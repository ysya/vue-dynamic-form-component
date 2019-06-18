# dynamic-form

## Component Prop

| prop            | description                                                  | type   | option values       | default | required |
| --------------- | ------------------------------------------------------------ | ------ | ------------------- | ------- | -------- |
| value           | form data                                                    | object |                     |         | yes      |
| lang            | language                                                     | string | en_US,zh_CN         | en_US   |          |
| descriptors     | descriptors of form data, refer to [descriptor](/zh/api/descriptor/) | object |                     |         | yes      |
| size            | size of form component                                       | string | medium,small,mini   | small   |          |
| backgroundColor | root form background color                                   | string | Hex color or 'none' | none    |          |
| fontSize        | font size of form                                            | number |                     | 14      |          |
| bgColorOffset   | form background color offset                                 | number |                     | 8       |          |

## Slots

| slot name  | description                                                 |
| ---------- | ------------------------------------------------------------ |
| operations | operation slot for form, use to put submit/reset button generally |

## Component Methods

| method        | description                                                 | params                                                       |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| validate      | validate the form. Takes a optional callback function as a param. Callback function will be executed with one param(validate result) while having the callback param. Return a promise(resolve validate result) without callback param. | Function(callback: (valid) => {}):void \| Function():Promise(Boolean) |
| resetFields   | reset form and remove validation result                      | () => {}                                                     |
| clearValidate | clear validation message of form                             | () => {}                                                     |

## Example

<code-demo name="form-demo"></code-demo>

<<< @/docs/.vuepress/components/form-demo.vue
