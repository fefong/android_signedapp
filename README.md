Android Application signing
=====================================

Example Application: Configuring signing with Java Key Store (JKS)

## Java Key Store
You can create or JKS or use any generated from another company, in this case is necessary use receved Alias and Password from access file.

#### SigningConfigs

- **storeFile:** path file your Java Key Store;
- **storePassword:** password Java Key Store;
- **keyAlias:** name internal Key;
- **keyPassword:** password internal Key;

<b>Important:</b> Not insert file Java Key Store internal app.
```java
android {
    ...
    signingConfigs {
        yourKey {
            storeFile file("C:/.../your_JKS.jks")
            storePassword "password"
            keyAlias "alias"
            keyPassword "password"
        }
    }
   ...
}
```
#### BuildTypes | BuildVariant
Make de references _yourKey_ and Android Build Variants.
```java
android {
    ...
    buildTypes {
        release {
          ...
         signingConfig signingConfigs.yourKey
        }
        debug {
          ...
         signingConfig signingConfigs.yourKey
         debuggable true
        }
    }
 }
```

Before updates is necessary project sync for the IDE  to work properly.


## Others
[KeyStore Explorer](https://keystore-explorer.org/index.html) - KeyStore Explorer is an open source GUI replacement for the Java command-line utilities keytool and jarsigner. KeyStore Explorer presents their functionality, and more, via an intuitive graphical user interface.
