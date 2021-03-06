# ROOM - STORIO - SQLITE

## What is this?

Through one simple example(registration module), i want to shows how to persist data using a ***Room***, ***Storio*** and ***SQLite***.
Our simple application stored only username and password, of course the real registration module is much more complex.

## Requirements

Android 5.0 or later (Minimum SDK level 21)

Android Studio 3.0 (to compile and use)

Eclipse is not supported


## Example insert operations for each API

        when (index) {
            GlobalConst.SQLITE -> {
                val contentValues = ContentValues()
                contentValues.put(GlobalConst.COL_2, userName)
                contentValues.put(GlobalConst.COL_3, password)
                sqlLiteDataBase.writableDatabase.insert(GlobalConst.USER_TABLE, null, contentValues)
            }
            GlobalConst.STORIO -> {
                val user = User()
                user.userName = userName
                user.password = password
                storioApi.addUser(user)
            }
            GlobalConst.ROOM -> {
                val userRoom = UserRoom()
                userRoom.userName = userName
                userRoom.password = password
                roomApi.insertUserRoom(userRoom)
            }
        }


## What does it look like?

![test image size](https://github.com/MilanBojic/registration_module/blob/master/image1.png)

![test image size](https://github.com/MilanBojic/registration_module/blob/master/image2.png)



**Support**

If you've found an error while using the library, please file an issue. All patches are encouraged, and may be submitted by forking this project and submitting a pull request through GitHub.
