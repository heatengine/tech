# Svelte

## Basic component structure
```
<script>
</script>

<!--
    The HTML code
-->

```

## $ - reactive property
```
$: 
```

## Conditions in HTML

```
{#if (<condition>)}

{:else if (<condition>)}

{:else}

{/if}
```

## Kinda interpolation
```
<script>
    let name = 'mr. foo';
</script>


<h1>Hello {name}!</h1>

```

## Looping in HTML

```
    {#each cats as cat, index} <!-- With index -->
		{cat.name}
	{/each}
```

```
<!-- referring using key (here thing.id) (any object can be used) -->
{#each things as thing (thing.id)}
	<Thing current={thing.color}/>
{/each}
```

## Async in HTML

```
{#await <promise returning var>}
	<p>...waiting</p>
{:then res} <!-- response -->

{:catch error}
	
{/await}
```

```
{#await promise then value}

{/await}
```

## Events
```
<div on:<event>|<modifier>={<handlerFunction>}></div>
```

```
LIST OF MODIFIERS
- preventDefault
- stopPropagation
- passive
- nonpassive
- capture
- once
- self
```

## Event Emission - (Dispatch)
```
import { createEventDispatcher } from 'svelte';

const dispatch = createEventDispatcher(); // Must be done when component is initiated

function sayHello() {
	dispatch(<eventName>>, <eventPayload>);
}

/**
 * on the receiver side `eventData.details` to access the payload
**/
```

- for nested components checkout [this](https://svelte.dev/tutorial/event-forwarding)

## Bind in inputs

```
<input bind:value={<js variable/property>} /> <!--  -->
<input bind:checked={<js variable/property>} />
<input bind:group={<js array>} />
```

## Select Multiple
```
<select multiple bind:value={<array>}>
	{#each <array> as item}
		<option value={item}>
			{item}
		</option>
	{/each}
</select>
```

## Editable HTML ()
```
<div contenteditable="true" bind:innerHTML={<jsProperty>}></div>
```

```
Bindings can be used with each
```

## Video and Audio tags
- Special properties for `<video>` and `<audio>` tags
	- duration
	- buffered
	- seekable
	- played
	- seeking
	- ended

## Reading dimensions 
- Every block-level element has `clientWidth`, `clientHeight`, `offsetWidth` and `offsetHeight` bindings

## `this` in Svelte
- The readonly this binding applies to every element (and component) and allows you to obtain a reference to rendered elements.
- Note that the value of canvas will be undefined until the component has mounted, so we put the logic inside the `onMount`.

## Lifecycle Functions
- onMount
- beforeUpdate
- afterUpdate
- onDestroy

##  Stores
- An object with `subscribe()` method
- Notifies the interested parties when value changes
- 'svelte/store'
- methods
	- derived() // created
	- readable() // creates a readable store
	- writeable() // creates a writable store
	- subscribe()
	- update() // for writable
	- set() // for writable
	- use $<store variable> to auto subscribe
	- store can be bind just like a variable

## Motions
### Tweened
- 'svelte/motion' & 'svelte/easing'
- tweened(<delay>, <options>);
```
tweened(delay, {
	duration,
	easing,
	interpolate
});
```
- methods `set()` & `update` to set or update the options

### Spring
- function `spring()`
- properties
	`stiffness`
	and
	`dumping` // amount of getting removed from something

### `transition` directive
- Use different functions from 'svelte/transition' to use different types of transitions
- Reversible nature

### `in` and `out` directive
- Used for in and out transitions

### Custom animations
```
function fade(node, {
	delay,
	duration
}) {
	return {
		delay,
		duration,
		css: t => `<pure css code>`
	};
}
```

### Transitions events
- introstart
- introend
- outrostart
- outroend

### local
- used to animation the when particular block is rendered
```
<someTag transition:<animation>|local>
```

### send and receive transition
```
<label
	class="done"
	in:receive="{{key: todo.id}}"
	out:send="{{key: todo.id}}"></label>
```



## Actions
### the `use` derective
- Actions are essentially element-level lifecycle functions.

- It can be better understood by (this)[https://svelte.dev/tutorial/actions] example.

## Classes
### `class` directive
```
<someTag class:<CLASS-NAME>:{<CONDITION>}></someTag>
<!-- also supports short hand when class name is equal to property -->
```


## Component compositions
### slot tag
- `<slot></slot>` used insert child that are written inside the opening and closing custom component
- Things written inside `<slot></slot>` will be the fallback if nothing is passed as child
- Use `name` property in `<slot></slot>` to use name slot and use `slot` property in child data tag to use particular slot
- `$$slots` variable to check if the particular slot is available
- Slots props


## BUILT-IN Components
### `<svelte:self>`
- As component can not import itself we can use `<svelte:self>` to re use the same component recursively
### `<svelte:component this={<component-ref>|<any-falsy-value>}>`
- Dynamically use any component skipping the conditions
### `<svelte:window>`
- Properties can be used - All except scrollX and scrollY are readonly.
	- `innerWidth`
	- `innerHeight`
	- `outerWidth`
	- `outerHeight`
	- `scrollX`
	- `scrollY`
	- `online` — an alias for window.navigator.onLine
### `<svelte:body />`
- Can be used to listen to events that are fired in `document.body` 
### `<svelte:head>`
- allows you to insert elements inside the `<head>` of your document
### `<svelte:options>`
- allows you to specify compiler options.
- Possible attributes to use
	- immutable={true} — you never use mutable data, so the compiler can do simple referential equality checks to determine if values have changed
	- immutable={false} — the default. Svelte will be more conservative about whether or not mutable objects have changed
	- accessors={true} — adds getters and setters for the component's props
	- accessors={false} — the default
	- namespace="..." — the namespace where this component will be used, most commonly "svg"
	- tag="..." — the name to use when compiling this component as a custom element
### `<svelte:fragment>`
- Similar to `<ng-container>` to use slot for more than one element without affecting the style

## Sharing code
- the following variable is sharable across all the module
```
<script context="module">
	let current;
</script>
```
- Anything exported from a `context="module"` script block becomes an export from the module itself.


# All about Svelte KIT (click here for official doc)[kit.svelte.dev/]

## Routing
- Svelte uses file path for routing

## REST Routing
## Fallthrough Routing

## Loading
- A component can export a `load` function which will run before the component is created
- It can take input `{ page, fetch, session, context }`
    - page = `{ host, path, params, query }`
    - fetch = `{ host, path, params, query }`
    - session = `{ host, path, params, query }`
    - fetch = `{ host, path, params, query }`
- It returns `{status, error, redirect, maxage, props, context}`


## Hooks (doc)[https://kit.svelte.dev/docs#hooks]
- getContext
- getSession
- handle

## Modules
### `$app/env`
- `amp` - 
- `browser` - running on the browser | server
- `dev`- dev | prod
### `$app/navigation`
- `goto(href, { replaceState, noscroll }): Promise`
- `prefetch(href)`
- `prefetchRoutes(routes)`
### `$app/paths`
- `base`
- `assets`
### `$app/stores`
- `getStores()`
- `navigating = { from, to }` - readable store 
- `page` - readable store whose value reflects the object passed to `load()`
- `session` -  whose initial value is whatever was returned from `getSession`.
### `$lib`
- simple alias to  `src/lib`
### `$service-worker`
- This module is only available to `service-workers`.
- `build` - an array of URL strings representing the files generated by Vite, suitable for caching with `cache.addAll(build)`
- `files` - array of URL strings representing the files in your static directory, or whatever directory is specified by `config.kit.assets`
- `timestamp` -  is the result of calling Date.now() at build time. It's useful for generating unique cache names inside your service worker, so that a later deployment of your app can invalidate old caches

## Service Worker
- 

## Anchor Options
- `sveltekit:prefetch` - 
- `sveltekit:noscroll` - will prevent scrolling after the link is clicked
- `rel=external` - will trigger a browser navigation when the link is clicked.
 
## Events
- `sveltekit:start` — fired once the app has hydrated
- `sveltekit:navigation-start` — navigation has started
- `sveltekit:navigation-end` — navigation has ended


# Render HTML from variables
## {@html <html as variable or string>}
```
{@html '<strong>Svelte is cool</strong>'}
```

# Reactivity
## Reactivity Statements
```
  // following condition is evaluated every-time the dependent property is updated
  $: if (count >= 10) {
    alert('count is dangerously high!')
    count = 9
  }
```
## Reactivity Expressions
```
  let number = 1;
  // following property is evaluated every-time the dependent property is updated
  $: square = number * number;
```

# Getting reference of a component in an `#each` block
```
<ChildComponent bind:this={<any var/array/obj to bind with>} />
```

# Rest Props - `$$restProps`
- `$$restProps` contains only the props which are not declared with `export`. It can be used to pass down other unknown attributes to an element in a component. It shares the same optimisation problems as $$props, and is likewise not recommended.

# Variables not values
- Svelte only care about the reassignment of the variables not the values it refers to.
- For more [click here](https://sveltesociety.dev/recipes/svelte-language-fundamentals/reactivity/)

