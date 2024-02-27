<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profile Database</title>

    <style>
        .banner {
            background-color: rgb(255, 149, 0);
            color: white;
            padding: 10px;
        }  
        #profile1List {text-align: left;}
        #profile2List {text-align: right;}
    </style>
</head>
<body>
    <div class="banner">
    <img src="file:///Users/rileymaguire/Downloads/rileygram-high-resolution-logo-transparent.jpg" alt="Riley gram">
    </div>

    <iframe src="https://thunkable.site/w/GI_4iEbUDX2fLwu1D3KJ0" width="100%" height="500px"></iframe>
    
    <h1>Profile List</h1>
    <ul id="profileList1"></ul>
    <ul id="profileList2"></ul>
    <script>
        import {getDatabase, set, get, update, remove, ref, child} from "firebase/database";
        // Import the functions you need from the SDKs you need
        import { initializeApp } from "firebase/app";
        import { getAnalytics } from "firebase/analytics";
        // TODO: Add SDKs for Firebase products that you want to use
        // https://firebase.google.com/docs/web/setup#available-libraries

        // Your web app's Firebase configuration
        // For Firebase JS SDK v7.20.0 and later, measurementId is optional
     </script>
     <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-app.js"></script>
     <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-database.js"></script> 
     <script>  
        var firebaseConfig = {
            apiKey: "AIzaSyAO6HErKfjojQhVLlz4Z5yh3xrNV2yKM0w",
            authDomain: "profileapp-a2c24.firebaseapp.com",
            databaseURL: "https://profileapp-a2c24-default-rtdb.firebaseio.com",
            projectId: "profileapp-a2c24",
            storageBucket: "profileapp-a2c24.appspot.com",
            messagingSenderId: "803426713563",
            appId: "1:803426713563:web:f0b211be62f3ae060571fe",
            measurementId: "G-S4DD4WGNN9"
        };

        // Initialize Firebase
        firebase.initializeApp(firebaseConfig);
        var database = firebase.database();


        //IDs
        var firstID = "WtXBRojlebVWEYGhPPjiHOiUoYA3";
        var secondID = "zUp7lliFPoM3AzpiosBNOAIqQCm2";
        

        var profileList = document.getElementById("profileList");

        function retrieveName(itemId, list){
            var itemRef = database.ref(itemId);
            itemRef.on("value", function(snapshot) {
                var data = snapshot.val();
                var name = data.name;
                var listItem = document.createElement("li");
                listItem.textContent = "Name: " + name;
                list.appendChild(listItem);
            });
        }

        function retrieveAge(itemId, list){
            var itemRef = database.ref(itemId);
            itemRef.on("value", function(snapshot) {
                var data = snapshot.val();
                var age = data.age;
                var listItem = document.createElement("li");
                listItem.textContent = "Age: " + age;
                list.appendChild(listItem);
            });
        }

        function retrieveMajor(itemId, list){
            var itemRef = database.ref(itemId);
            itemRef.on("value", function(snapshot) {
                var data = snapshot.val();
                var major = data.major;
                var listItem = document.createElement("li");
                listItem.textContent = "Major: " + major;
                list.appendChild(listItem);
            });
        }

        function retrieveHometown(itemId, list){
            var itemRef = database.ref(itemId);
            itemRef.on("value", function(snapshot) {
                var data = snapshot.val();
                var hometown = data.hometown;
                var listItem = document.createElement("li");
                listItem.textContent = "Hometown: " + hometown;
                list.appendChild(listItem);
            });
        }

        //First Profile
        retrieveName(firstID, profileList1);
        retrieveAge(firstID, profileList1);
        retrieveMajor(firstID, profileList1);
        retrieveHometown(firstID, profileList1);

        //Second Profile
        retrieveName(secondID, profileList2);
        retrieveAge(secondID, profileList2);
        retrieveMajor(secondID, profileList2);
        retrieveHometown(secondID, profileList2);
        
    </script>

    
    </body>
</html>
