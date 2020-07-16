# VueJS Gauge Chart


> A vuejs gauge charts wrap-over for the library [gauge-chart](https://github.com/recogizer/gauge-chart) .

## [Demo](https://recogizer.github.io/gauge-chart/examples/samples/)

### Installation
```bash
npm install vue-gauge
```

### Example

```vue

<template>
  <vue-gauge :refid="'type-unique-id'"></vue-gauge>
</template>

<script>
  import VueGauge from 'vue-gauge';
  export default {
    components: { VueGauge },
  }

</script>

Or to load as global component

<script>
  import VueGauge from 'vue-gauge';
  Vue.component('vue-gauge', VueGauge);
</script>
```


By default, the needle is pointing to 70, thus in order to move it you have to use like below

```vue
<template>
  <vue-gauge :refid="'type-unique-id'" :options="{'needleValue':85,'arcDelimiters':[85]}"></vue-gauge>
</template>
```

You can also change others gauge options value like:

```vue
<template>
  <vue-gauge :refid="'type-unique-id'" :options="{'needleValue':85,'arcDelimiters':[10,36,78], 'hasNeedle':false]}"></vue-gauge>
</template>

```

## Options


| Name              | Values Ranges                                                                    | Description                                          |
| ----------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| hasNeedle         | true / false                                                                     | determines whether to show the needle or not                        |
| needleColor       | [value supported by CSS](https://www.w3schools.com/colors/default.asp)           | colorizes needle with specified colors                              |
| needleUpdateSpeed | number ⩾ 0                                                                       | determines the speed of needle update animation                     |
| arcColors         | [array of values supported by CSS](https://www.w3schools.com/colors/default.asp) | colorizes gauge with specified color                                |
| arcDelimiters     | array of numbers from 0 to 100                                                   | specifies delimiters of the gauge in ascending order                |
| arcOverEffect     | true / false                                                                     | determines if over effect on ars is enabled or not                  |
| arcLabels         | array of strings                                                                 | specifies labels to be placed at delimiters ends                    |
| arcPadding        | number                                                                           | specifies padding between arcs (in pixels)                          |
| arcPaddingColor   | [value supported by CSS](https://www.w3schools.com/colors/default.asp)           | color of the padding between delimeters                             |
| rangeLabel        | array of two strings                                                             | depicts gauge ranges on both sides of the chart                     |
| centralLabel      | string                                                                           | depicts gauge inner label                                           |
| labelsFont        | string                                                                           | specifies font-family to be used for labels                         |
| chartWidth        | number larger than 0                                                             | gives a width to the gauge (height is always 0.5 \* chartWidth)     |
| needleValue       | number from 0 to 100                                                             | specifies needle value on the gauge                                 |


## Examples

Some examples of what you can get out of the library using different properties:

![Gauge Examples](https://github.com/Md-Razu-Haolader/Vue-Gauge/blob/master/demo/gauges.png 'Gauge Examples')





