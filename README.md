# polymer-calendar-datepicker

**This element is compatible with Polymer 0.5.**

__Example:__

```
	<polymer-element name="polymer-daterange-picker-example">
		<template>
			<div class="startPicked"><strong>Start</strong> {{ startPicked | momentDisplay }}</div>
			<div class="endPicked"><strong>End:</strong> {{ endPicked | momentDisplay }}</div>
			<polymer-daterange-picker ranges="{{ranges}}" selected="{{selected}}" startPicked="{{startPicked}}" endPicked="{{endPicked}}"></polymer-daterange-picker>
		</template>
		<script src="../moment/moment.js"></script>
		<script>
		Polymer({
			ranges: [
				{
					label: "Today",
					handler: function(e) {
						this.startPicked = moment().startOf('day').format();
						this.endPicked = moment().format();
					}
				},{
					label: "This Week",
					handler: function(e) {
						this.startPicked = moment().startOf('week').format();
						this.endPicked = moment().format();
					}
				}
			],
			selected: 1,
			startPicked: moment().startOf('week').format(),
			endPicked: moment().format(),
			momentDisplay: function(data) {
				if(data) {
					return moment(data).format('MM-DD-YYYY');
				}
				return;
			}
		});
		</script>
	</polymer-element>
	<polymer-daterange-picker-example></polymer-daterange-picker>
```
# Attributes

#### `ranges`

An array of objects. Each object expects label and handler properties.

#### `selected`

Integer selecting an item from ranges