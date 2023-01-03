# Tailwind CSS


<!-- [tailwind tutorial](https://github.com/thusspokedata/tailwind-sandbox/tree/main/tailwind-sandbox-done) 

<hr/>-->
<ul>
<li>Tailwind CSS is a set of predefined CSS classes.</li>
<li>It is essentially writing CSS code directly in the HTML.</li>
<li>The main part of Tailwind CSS philosophy is HTML first, the idea is that we stay in the HTML as much as possible.</li>
<li>One of the main problems we avoid with Tailwind CSS is naming the classes.</li>
<li>Tailwind is fully customizable to our theme and we can also overwrite any of these existing presets.</li>
<li>Tailwind uses a default layout which is 'Mobile First'.</li>
<li>The versatility of Tailwind CSS sometimes causes us to generate very long lines of code. We will also often find ourselves in situations where we are repeating our code. Fortunately, using React (or Vue) allows us to create components we can reuse.</li>
<li>We can also apply all Tailwind classes within a self-created CSS file, where using @apply would allow us to use multiple Tailwind classes in a single reusable class name.</li>
<li>We can also add new CSS rules using its configuration file called tailwind.config.cjs.</li>
<li>The biggest advantage that we will see in Tailwind CSS is its optimization when going to production. That is, at development time, Tailwind can weigh up to 3 MB because we can use all its features, but in production, not all the classes are necessary, so Tailwind will generate a CSS file leaving only the classes we are using, massively reducing the weight of our styles and allowing our site to load faster. This is possible because Tailwind also uses PostCSS (which is a CSS preprocessor), which does this job.</li>
</ul>

<h3>Some useful extensions when using Tailwind:</h3>

<p>Tailwind CSS Intellisense</p>
<p>CSS Peek</p>

<h3>Some sites of interest:</h3>

<a href="https://flowbite.com" target="_blank">Flowbite</a><br>
<a href="https://tailwind-elements.com" target="_blank">Tailwind-elements</a><br>
<a href="https://tailwinduikit.com" target="_blank">Tailwinduikit</a><br>
<a href="https://tailwindcomponents.com" target="_blank">Tailwindcomponents</a><br>
<a href="https://tailwindui.com" target="_blank">Tailwindui</a><br>

<br>
<hr/>


<p>Tailwind gives us the ability to define our styles, but how do we make this work within our components? components will accept props and we need to conditionally assign classes based on these props thar are passeed in. A common solution to this is to use something like class names or "<a href="https://www.npmjs.com/package/clsx" target="_blank">clsx</a>". "clsx" works very well if we only have one prop that's being passed in, but this could get really complicated if we have like 10 or 12 props. 
<p>This is where <a href="https://www.npmjs.com/package/class-variance-authority" target="_blank">Class Variance Authority (CVA)</a> comes in. CVA gives us an easy to use interface to define variants, which conditionally apply set of classes. CVA can also express default variants and even compound variants where classes can be applied based on a convination on variants. </p>
<p>As a nice side effect, the Typescript type of variants is also super easy to incorporate into your component using the variant props type helper.</p>


<p>With TypeScript, we can set up a path alias. So this lets us import our UI components from a consistent path instead of a relative path. We can set up '@ui/' to basically point to the folder that our UI components are in.</p>

```ts
{
  "compilerOptions": {
    "target": "es2017",
    "lib": ["dom", "dom.iterable", "esnext"],
    "allowJs": true,
    "skipLibCheck": true,
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "noEmit": true,
    "esModuleInterop": true,
    "module": "esnext",
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "jsx": "preserve",
    "incremental": true,
    "noUncheckedIndexedAccess": true,
    "paths": {                        
		 "@ui/*": ["./src/components/ui/*"]  // <---- here
	 }
  },
  "include": ["next-env.d.ts", "**/*.ts", "**/*.tsx", "**/*.cjs", "**/*.mjs"],
  "exclude": ["node_modules"]
}
```

<br>
<hr/>


<p><a href="https://www.npmjs.com/package/storybook" target="_blank">Storybook</a> is an isolated component playground where we can test our components outside the context of our application.</p>
<p>This is critical when building UI components libraries because it lets us avoid running the entire app to test all the states of the different components we build.</p>
<p>For example, we can have a delete button that only appears on a specific page. In Storybook, we can render the delete button component and change the props however you please and see how it looks based on the different props.</p>


