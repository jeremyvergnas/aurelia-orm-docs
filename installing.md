# Installing

Head over to your terminal of choice, and navigate to your project.
Now run the following command:

`jspm i aurelia-orm aurelia-api`

This will install aurelia-orm and [aurelia-api](https://github.com/SpoonX/aurelia-api).

## Configuring

Aurelia-orm uses [aurelia-api](https://github.com/SpoonX/aurelia-api) to talk to the server. By default, it will communicate with the domain you're hosting your app on. If you wish to change the endpoints used, you should take a look at configuring aurelia-api.

### Registering entities

Upon configuration you can register your entities. Code speaks louder than words, so here's an example:

```js
// Import your entities
import * as entities from 'config/entities';

export function configure(aurelia) {
  aurelia.use
    .standardConfiguration()
    .developmentLogging()

    // Register the plugin, and register your entities
    .plugin('spoonx/aurelia-orm', builder => {
      builder.registerEntities(entities);
    });

  aurelia.start().then(a => a.setRoot());
}
```

Here's what your `config/entities.js` file might look like:

```js
export {User} from 'entity/user';
export {Article} from 'entity/article';
export {Category} from 'entity/category';
```
