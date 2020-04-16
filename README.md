# vue-material-input-box

Simple and lightweight material design input component with no dependencies.

## Showcase

![Showcase](https://raw.githubusercontent.com/mehmetkarakamis/vue-material-input-box/master/screenshots/vue-material-input-box.gif)

## Installation

```bash
npm i vue-material-input-box --save
```

## Usage

In your `main.js` file, register the component:

```javascript
import Vue from "vue"

import VueMaterialInputBox from "vue-material-input-box"
Vue.component("VueMaterialInputBox", VueMaterialInputBox);
```

Example:

```html
<VueMaterialInputBox 
	label="Full name"
	v-model="full_name"
/>
```
## Props
<table>
	<thead>
		<tr>
			<th>Prop</th>
			<th>Type</th>
			<th>Default</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>autocomplete</td>
			<td>String</td>
			<td>"off"</td>
		</tr>
		<tr>
			<td>background-color</td>
			<td>String</td>
			<td>"#FAFAFA"</td>
		</tr>
		<tr>
			<td>color</td>
			<td>String</td>
			<td>"#2196F3"</td>
		</tr>
		<tr>
			<td>disabled</td>
			<td>Boolean</td>
			<td>false</td>
		</tr>
		<tr>
			<td>label</td>
			<td>String</td>
			<td>null</td>
		</tr>
		<tr>
			<td>placeholder</td>
			<td>String</td>
			<td>null</td>
		</tr>
		<tr>
			<td>required</td>
			<td>Boolean</td>
			<td>false</td>
		</tr>
		<tr>
			<td>type</td>
			<td>String</td>
			<td>"text"</td>
		</tr>
	</tbody>
</table>