
> Created Wednesday 6 Sept 2023 at 22:34 PM
## Motivation

- wanted a way to write web type of classes in `react native`


## Library(s)  that are available

1. [NativeWind](https://www.nativewind.dev/) - simple code look similar to web. using className prop we can add.
2. [twnc](https://www.npmjs.com/package/twrnc) - good alternative but syntax is very different like in `<Text style={tw`text-neutral-100`}>Hello</Text>
3. [tailwind-rn](https://www.npmjs.com/package/tailwind-rn)- another alternative `<Text style={tailwind('text-blue-800 font-semibold')}>Hello</Text>`
4. [RN zephyr](https://formidable.com/open-source/react-native-zephyr/) - [TailwindCSS](https://tailwindcss.com/)-inspired styling library for React Native.

- I personally liked `NativeWind`

## NativeWind features

RN code comparision 

```jsx

<View>
	<Text className="font-bold underline">
	  native wind classes
	</Text>
	<Text style={{
		fontWeight:"bold",
		textDecoration:underline;
	}}>
	  RN way of classes
	</Text>
</View
```

>Claimed features

- Works on **all** RN platforms, uses the best style system for each platform.
- Uses the Tailwind CSS compiler
- Styles are computed at **build time**
- Small runtime keeps your components fast
- Babel plugin for **simple setup** and improving **intellisense support**
- Respects all tailwind.config.js settings, including **themes, custom values, plugins**
- **dark mode / arbitrary classes / media queries**
- pseudo classes - **hover / focus / active** on compatible components
- styling based on **parent state** - automatically style children based upon parent pseudo classes
- **children styles** - create simple layouts based upon parent class

For arbitary value- colors like `text-[#ff0000]` and sizing `w-[100px]` also work. this will help us to use specific arbitrary value at some places but it is not suggested to do at most places because we should stick to a design system in case of product design.


# setting Up nativewind

- For updated result use nativeWind [docs](https://www.nativewind.dev/quick-starts/react-native-cli) Note:- I'm using react-native-cli so docs added are of that you can switch to expo from menu if using expo.
- add content in `tailwind.config.js`
```js
content: [ "./App.{js,jsx,ts,tsx}", 
			"./src/**/*.{js,jsx,ts,tsx}",
			"./src/components/**/_.{js,jsx,ts,tsx}", 
			"./src/screens/**/_.{js,jsx,ts,tsx}", 
			// add all other custom paths
		],
```
- to override specific style in when adding styles add this to `tailwind.config.js`.
```js
    const defaultTheme = require("tailwindcss/defaultTheme"); // add

theme{
// all other things
fontFamily: { 
	sans: ["Manrope", ...defaultTheme.fontFamily.sans], },
}
```
- 🙌 now every property of web we can use



## common problems and fixes
1. "process(cb)" issue - two steps here:
    1. Lower the version to 3.2.2 [StackOverflow](https://stackoverflow.com/a/76700786/11392807)
    2. If the issue persists, a restart will fix.



