# Entities

> An instance or class of type `Entity` that defines, and holds the data of a single resource record.

Entities represent the schema of your resources. They can hold validation rules, associations, type hinting and more. In this chapter, we'll be looking at what an entity looks like, how you can create one and what they're responsible for.

## Creating

By default, aurelia-orm works with all resources, even if you don't supply a custom entity. When this happens, your entities won't have any decoration and aurelia-orm will allow all values to be set as-is.

But if you do want all these fizzy good make feel nice features, you'll want to keep on reading.

![](http://media.tumblr.com/tumblr_m8vsn5EwG61r1c47w.gif)

### The class

Creating an entity is simple.

```js
import {Entity} from 'aurelia-orm';

class Product extends Entity {
}
```

That's it! That's all that's needed to create an entity.

### Registering

After creating your gem of an Entity, you'll want to register it with the EntityManager. That way, the Repository responsible for your resource will populate using your new entity!
