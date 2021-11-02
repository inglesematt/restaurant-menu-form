Hi Chris, Liga and team,

I hope you like the menu layout. Here are some of the technical steps and sources I've used to get there.

Kind regards,
Matthew

---

Navigation:

Using Vue Router

Source:
Udemy VueJS course with Net Ninja.

Menu:

Mounted the API using Fetch() and iterated over the JSON using v-for.
Used CSS grids areas to create the responsive display.

Sources:
Codecademy VueJS course / Udemy VueJS course with Net Ninja / Net Ninja YouTube & vuejs.org for some syntax.

Form:

Vue js form employing standard inputs, textarea and checkbox. Uses a method to authenticate the email and a computed method to disable the submit button until the form has the required fields. Additional css styles to nudge user to correct authentication on email and an event listener to alert successful submit message (users can only submit when email authenticated and required fields filled - therefore no need for failure message)

Sources:
Codecademy VueJS course / Udemy VueJS course with Net Ninja / vuejs.org for documentation around email authentication.

Sharing:

I have uploaded to a Github repository: https://github.com/inglesematt/restaurant-menu-form

and the app/site is deployed on Firebase: https://restaurant-menu-form.web.app/

# menu-layout

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
