---
title: "How to Store ID in Local Storage Angularjs"
date: 2017-11-03T23:28:54+08:00
draft: false
---

![AngularJS Local Storage](/image/20171103/local-storage-angularjs.png)
<sub><sup>Icon from VectorBakery and Adnen Kadri </sup></sub>

## Requirement
[Angular storage](https://github.com/auth0/angular-storage)
 
### What type of information can be store in local storage?
Most of the website store information in local storage such as token, service id,
 
Let’s code
I want to create a function to the website to store the member id after the user successfull login the website. The input will be a member id get from rest api and website able to use the getter function to get the member id from local storage.
 
Why need to store?
The member id can be use for various reasons. It can be use in rest api to get information for specific members.
 
### Introduction to Angular Storage
I’m using angular storage to store the because it’s extremely simple. This is an example to store a value in localstorage. First of all, inject **‘angular-storage’** into your website.

```javascript
angular.module('my-app', ['angular-storage']);
```


Make sure to have store as the parameter function to use the angular storage.
This will create a key as bank with a value 1600 and store it in the local storage.

```javascript
store.set('bank', 1600);
```


This is how the value stored in local storage. 
![Value stored in Local storage](/image/20171103/chrome-local-storage.png)


To get the value you can simply use this. It accept a key as parameter to get the value.
```javascript
store.get('bank');
```


### Write a factory
We need to store the information, so let’s write a factory in Angularjs. Inject the factory into the module. Don’t forgot to include store as parameter in the function.
angular.module('ng-starter.index').factory('memberIdService', function (store){}                                                                   



I will assign a member id into memberId in the local storage. This is full code of factory.

```javascript
angular.module('ng-starter.index').factory('memberIdService', function (store){
	
        var currentId = null;

        return function(memberId){

          if (memberId) {
            currentId = memberId;
            store.set('memberId', currentId);
          }
          if (!currentId) {
            currentId = store.get('memberId');
          }

          return currentId;

        }

    });

```



There are two different output in this function. If no memeber ID passed in the function, the function will return the member ID from local storage. But, if there is a member Id passed, it will store in a local storage.
What if there is a same key in the local storage?
The value will be overwrite.
 
### How to use?

Main purporse of this code is to store member ID when the user successful login. Let’s use this code in login controller. First of all, import the the factory that we write just now into the function.
I’m using **$http** to interact with REST API. If the $http successfull request, it will run the function in the **memberIdService(res.data.userId)** . This is how we passed the member Id from REST API into factory we just wrote.

```javascript

 function RegisterController($scope, $http, memberIdService) {
  
      $http({
          method: 'POST',
          url: 'http://localhost/user/login',
          data: $scope.signin,
          headers: {
            'Content-Type': 'application/json; charset=utf-8'
          }
        })
        .then(function(res) {
          $log.info('Successfully logged in member:', res.data);
          memberIdService(res.data.userId);
        }
        .catch(function (error) {
           console.log(error);
           toastr.warning('Wrong username or password.', 'Warning');
          });   
 }

 ```




