# EZobject2xml
_by Alexandre CHAPELLE_

The aim of this module is to easily save and load any object data into/from a xml file.

This module has only one object "xmltool" with 2 functions:

#### For saving an object into a xml file, you just have to:
```python
myXmltool = xmltool()

myXmltool.saveObject2xml(myObject,myFilename)
```

where:

_myObject_ is the object to save

_myFileName_ if the xml file

#### And for loading:
```python
myXmltool.loadObjectFromXml(myObject,myFilename)
```

#### Exception:
If objects have to be dynamically initialized during the data reading process
(i.e. if your object has a list of an undefined number of other objects), 
we have to create them first before reading their saved data.
In order to do that, we give a list of object class that we could use to create a new instance of these objects.

This list of class objects is a initDataList object and we pass it as:
```python

myInitDataList = initDataList()

myInitDataList.addInitData(mySubObject1Class,(a tuple containing the parameters to initialize this SubObject))

myInitDataList.addInitData(mySubObject2Class,(a tuple containing the parameters to initialize this SubObject))

...

myXmltool.loadObjectFromXml(myObject,myInitDataList)
```

As seen, myInitDataList is optional and only needed when your object has a list of an undefined number of other objects.

Please see the help() to see more technical information about these functions.

