## Slides are marked with an arrow
---

`→ History API & Routing`

Theme of this presentation is History API & Routing

`→ History`

The History interface allows manipulation of the browser session history, that is the pages visited in the tab or frame that the current page is loaded in.
History interface has some properties

`→ Properties`

`→ length`

length - returns the number of pages that you have visited for the current tab.

`→ scrollRestoration`

scrollRestoration. It defines the behavior after a reload of the current page. There is 2 values possible:

- `→ auto:`

  - if the user has scrolled, then after reloading the page, the page will automatically scroll where the user was before.

- `→ manual:`
  - after reloading the current page, the user will be at the top of the page wherever the user was on the page before.

Last property is state

`→ state`

state is a sort of context in which you can store any values (that can be serialized) that needs to be kept when going to the next page. Each page has its own state.
state - returns the state for the current page you are. This value cannot be changed.
History interface has some methods

`→ Methods`

`→ back()`

Method back.
This method goes to the previous page in session history, the same action as when the user clicks the browser's Back button

`→ Example: go`

`→ If we have THIS history stack`

`→ After executing this method`

`→ We got THIS history stack`

`→ forward()`

Method forward.
This method goes to the next page in session history, the same action as when the user clicks the browser's Forward button

`→ Example: go`

`→ If we have THIS history stack`

`→ After executing this method`

`→ We got THIS history stack`

`→ go()`

go
This method loads a page from the session history, identified by its relative location to the current page, If you specify an out-of-bounds value (for example, -1 when there are no previously-visited pages in the session history), this method silently has no effect. Calling go() without parameters or a value of 0 reloads the current page.

`→ Example: go`

`→ If we have THIS history stack`

`→ After executing this method`

`→ We got THIS history stack`

`→ pushState`

method pushState.
This method allows you to push an entry in the history. It takes as parameters:

- `→ state: the state for the new entry`
- `→ title: You can pass a string if you want to define a title for the new state. Note that, nowadays, this parameter is not used by browsers`
- `→ url: this parameter is optional, it defines the new entry url if you want to change it. You can path a relative or absolute path until you stay on the same origin. This new url will not be loaded by your browser.`

`→ Example: pushState`

`→ If we have THIS history stack`
`→ After executing this method`
`→ We got THIS history stack`

`→ replaceState`

method replaceState.
This method allows you to replace to current entry in the history. It takes the same parameter as pushState:

- `→ state`

- `→ title`

- `→ url`

`→ Example: replaceState`

`→ If we have THIS history stack`

`→ After executing this method`

`→ We got THIS history stack`

`→ clear slide`

Thats All about History API

`→ Routing`

Routing - The process that is responsible for determining the handler for a particular requested page is called routing.

`→ Example`

Each address in the example represents a specific route. Moreover, they can be divided by type: static and dynamic.

`→ Static routes`

Static routes
Characterized by the fact that the address matches the route itself.
For example

`→ account/profile/edit`

Despite the fact that the address is the same, it will display different data for different users, depending on who is currently authorized.

`→ Dynamic routes`

But what if we have addresses that mean the same thing, but contain a parameter.
Typical example

`→ /users/5`

Without much difficulty, you can understand that using this link we will get information about user number 5. But then the question arises: if we have thousands of users in the database, will we have to define thousands of routes?
Luckily, no, this is where regular expressions come to the rescue. A single route is created that looks something like this:

`→ ^/users/(\w+)`

And then you just need to match this regular expression with the query string. In other words, we have defined one single route that covers similar links:

`→ Links example`

After this point, it becomes clear that the routing process is a little more complicated than just a big if or switch.

`-> clear slide`

That is all. Thank you for watching.
