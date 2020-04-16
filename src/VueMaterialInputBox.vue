<template>
	<div class="container">
		<input
			class="input"
			:autocomplete="autocomplete"
			@focus="push_from_bottom = true"
			@blur="onBlur"
			:disabled="disabled"
			@input="handleInput"
			:placeholder="placeholder"
			:required="required"
			:style="{ 'background-color': backgroundColor }"
			:type="type"
		>
		<div
			class="bar"
			:style="{ color: color }"
		></div>
		<label
			class="label"
			:class="{ 'push-from-bottom': push_from_bottom }"
			:style="{ color: push_from_bottom ? color : 'rgba(0, 0, 0, 0.6)' }"
		>{{ label }}</label>
	</div>
</template>

<script>
	export default {
		name: "VueMaterialInputBox",
		props: {
			autocomplete: {
				default: "off",
				type: String
			},
			backgroundColor: {
				default: "#FAFAFA",
				type: String
			},
			color: {
				default: "#2196F3",
				type: String
			},
			disabled: {
				default: false,
				type: Boolean
			},
			label: {
				default: null,
				type: String
			},
			placeholder: {
				default: null,
				type: String
			},
			required: {
				default: false,
				type: Boolean
			},
			type: {
				default: "text",
				type: String
			}
		},
		data() {
			return {
				input_value: null,
				push_from_bottom: false
			}
		},
		created() {
			if(this.placeholder) this.push_from_bottom = true;
		},
		methods: {
			handleInput(event) {
				this.input_value = event.target.value;
				this.$emit("input", this.input_value);
			},
			onBlur() {
				if(!this.input_value && !this.placeholder) this.push_from_bottom = false;
			}
		}
	}
</script>

<style scoped>
	.container {
		position: relative;
		width: 100%;
	}
	.input {
		padding: 10px 15px 10px 5px;
		display: block;
		border: none;
		border-bottom: 2px solid #D4D4D4;
		color: rgba(0, 0, 0, 0.87);
		width: 100%;
	}
	.input:focus {
		border-bottom: none;
		outline: none;
	}
	.bar:before, .bar:after {
		background-color: currentColor;
		content: "";
		height: 2px;
		position: absolute;
		transition: all ease 0.30s;
		width: 0;
	}
	.bar:before { left: 50% }
	.bar:after { right: 50% }
	.input:focus ~ .bar:before, .input:focus ~ .bar:after { width: 50% }
	.label {
		bottom: 10px;
		font-size: 17px;
		left: 5px;
		pointer-events: none;
		position: absolute;
		transition: all ease 0.30s;
	}
	.push-from-bottom {
		bottom: 45px;
		font-size: 14px;
	}
</style>