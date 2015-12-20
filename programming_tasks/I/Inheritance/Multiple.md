[1]: http://rosettacode.org/wiki/Inheritance/Multiple

# [Inheritance/Multiple][1]

```perl6
class Camera {}
class MobilePhone {}
class CameraPhone is Camera is MobilePhone {}
 
say CameraPhone.^mro;     # undefined type object
say CameraPhone.new.^mro; # instantiated object
```

#### Output:
```
CameraPhone() Camera() MobilePhone() Any() Mu()
CameraPhone() Camera() MobilePhone() Any() Mu()
```


The <tt>.^mro</tt> is not an ordinary method call,
but a call to the object's metaobject
that returns the method resolution order for this type.