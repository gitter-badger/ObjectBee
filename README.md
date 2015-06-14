ObjectBee
=======

A simple data transporte library


Download
--------

Download [the latest JAR][2] or grab via Gradle:
```groovy
compile 'ihsan.bal.objectbee:xxx'
```
or Maven:
```xml
<dependency>
  <groupId>ihsan.bal.objectbee</groupId>
  <artifactId>objectbee</artifactId>
  <version>x.x.x</version>
</dependency>
```

Snapshots of the development version are available in [Sonatype's `snapshots` repository][snap].



Usage
--------
You must to create data model extends BaseBeeModel
```java
package ihsan.bal.library.base;

import java.io.Serializable;

/**
 * Created by ihsan on 23/05/15.
 */
public class BaseBeeModel implements Serializable {

    public boolean deletepullobject;

    public String referencesname;
    /*
    * default ok_response code 100
    * error_response code 99
    * */
    public int responsecode = 100;

    public String responsemessage;

    public BaseBeeModel(String referencesname){
        if (referencesname!=null)
        this.referencesname = referencesname;
    }

}
```
Example Data Model
```java
package ihsan.bal.library.base;

/**
 * Created by ihsan on 23/05/15.
 */
public class BaseModel extends BaseBeeModel {
    public String title;

    public BaseModel() {
        super("BaseModel");
    }
}
```

If you want do save data and start activity
```java
BaseModel model = new BaseModel();
        model.title = "Pushed A model";
Bee.with(this).been(model).pushAndStart(DetailActivity.class);
```



Licence
--------------
Copyright 2015 İHSAN BAL

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

Author
--------------
[İHSAN BAL](https://github.com/ihsanbal)
