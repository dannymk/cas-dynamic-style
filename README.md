**DO NOT USE THIS FOR PRODUCTION.  It is only here as a way to figure out the dynamic styles**

Based on:  https://apereo.github.io/cas/development/ux/User-Interface-Customization-Themes.html

## Requirements
 - Linux or Mac system
 - Docker
 - git

# Build and test dynamic styles for the CAS interface

1. git clone https://github.com/dannymk/cas-dynamic-style.git
2. cd cas-dynamic-style
3. git clone https://github.com/apereo/cas-overlay-template.git
4. edit the file __cas-overlay-template/build.gradle__ and add the following missing lines (as of this writting around line 74...)
```sh
dependencies {
    // Other CAS dependencies/modules may be listed here...
    // implementation "org.apereo.cas:cas-server-support-json-service-registry:${casServerVersion}"
    implementation "org.apereo.cas:cas-server-support-json-service-registry:${casServerVersion}"
    implementation "org.apereo.cas:cas-server-support-generic:${casServerVersion}"    
}
```
5. sh runBuild
6. sh run
7. Navigate to http://localhost:8080/cas/login
You will get the default template here...
8. Navigate to http://localhost:8080/cas/login?service=http://mydomain.com
You will get the template defined as "foo"
