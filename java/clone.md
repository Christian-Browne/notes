# Clone

```java
public Microscope(Microscope source) {
        super(source);
        setMagnification(source.magnification);
    }

    /* Don't have to call new Microscope(source) everytime can do
    .clone() instead */
    // Functions are the same, this is just is a shorthand now
    @Override
    public LabEquipment clone() {
        return new Microscope(this);
    }
```
