<template lang="pug">
  component-view(v-bind:doc="doc")
</template>

<script>
  export default {
    data () {
      return {
        doc: {
          title: 'Chip',
          component: 'VChip',
          edit: 'ChipsView',
          desc: `The <code>v-chip</code> component is used to convey small pieces of information. Using the <code>close</code> property, the chip becomes interactive, allowing user interaction.`,
          examples: [
            { header: 'Default', file: 'chips/default', desc: 'Chips come in 4 primary variations. Regular, with icon, with portrait and closeable.' },
            { header: 'Colored', file: 'chips/colored', desc: 'Any color from the Material Design palette can be used to change a chips color.' },
            { header: 'Icon', file: 'chips/icon', desc: 'Chips can use text or any icon available in the Material Icons font library.' },
            { header: 'Outline', file: 'chips/outline', desc: 'Outlined chips inherit their border color from the current text color.' },
            { header: 'Label', file: 'chips/label', desc: 'Label chips use the <code>v-card</code> border-radius.' },
            { header: 'Closable', file: 'chips/closable', desc: 'Closable chips can be controlled with a v-model. Listen to the <code>input</code> event if you want to know when a chip has been closed.' },
            { header: 'In selects', file: 'chips/in-selects', desc: 'Selects can use chips to display the selected data.', new: '0.15.3' }
          ],
          props: {
            'v-chip': {
              shared: ['colorable', 'theme'],
              params: [
                [
                  'text-color',
                  'String',
                  'null',
                  'Applies specified color to the control text'
                ],
                [
                  'close',
                  'Boolean',
                  'False',
                  'Adds remove button'
                ],
                [
                  'disabled',
                  'Boolean',
                  'False',
                  'Disabled the chip from being selectable'
                ],
                [
                  'label',
                  'Boolean',
                  'False',
                  'Applies the chip--label class'
                ],
                [
                  'outline',
                  'Boolean',
                  'False',
                  'Applies the chip--outline class'
                ],
                [
                  'small',
                  'Boolean',
                  'False',
                  'Applies the chip--small class'
                ],
                [
                  'selected',
                  'Boolean',
                  'False',
                  'Applies a selection color to the chip. Primarily used for displaying highlight context in <code>v-select</code>'
                ]
              ],
              model: {
                type: ['Boolean'],
                default: 'True'
              }
            }
          },
          slots: {
            'v-chip': {
              shared: ['default']
            }
          },
          events: {
            'v-chip': {
              params: [
                ['input', 'Boolean: False', "Chip was closed. Requires 'close' prop."]
              ]
            }
          }
        }
      }
    }
  }
</script>

<style lang="stylus">
  #chips-view
    .component-example__container > div
      text-align: center

    .chip
      margin: 1rem
</style>
