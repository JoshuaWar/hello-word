# EZobject2xml
by Alexandre CHAPELLE

The aim of this module is to easily save and load any object data into/from a xml tool.

This module has only one object "xmltool" with 2 functions.
_For saving an object into a xml tool, you just have to:_
myXmltool = xmltool()
myXmltool.saveObject2xml(myObject,myFilename)
_And for loading:_
myXmltool.loadObjectFromXml(myObject,myFilename)

## Exception: ##
If objects have to be dynamically initialized during the data reading process
(i.e. if your object has a list of an undefined number of other objects), 
we have to create them first before reading their saved data.
In order to do that, we give a list of object class that we could use to create a new instance of these object.
_This list of class objects is a initDataList object and we pass it as:_
myInitDataList.addInitData(mySubObject1Class,(a tuple containing my parameters to initialize this SubObject))
myInitDataList.addInitData(mySubObject2Class,(a tuple containing my parameters to initialize this SubObject))
...
myXmltool.loadObjectFromXml(myObject,myInitDataList)

As seen, myInitDataList is optional and only needed when your object has a list of an undefined number of other objects.

Please see the help() to see more technical information about these functions.
