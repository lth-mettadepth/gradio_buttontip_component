---
tags: [gradio-custom-component, ]
title: gradio_buttontip_component
short_description: A gradio custom component
colorFrom: blue
colorTo: yellow
sdk: gradio
pinned: false
app_file: space.py
---

# `gradio_buttontip_component`
<a href="https://pypi.org/project/gradio_buttontip_component/" target="_blank"><img alt="PyPI - Version" src="https://img.shields.io/pypi/v/gradio_buttontip_component"></a>  

Python library for easily interacting with trained machine learning models

## Installation

```bash
pip install gradio_buttontip_component
```

## Usage

```python

import gradio as gr
from gradio_buttontip_component import buttontip_component


def button_click(a,b):
    return "Button clicked!"

demo = gr.Interface(
    title="Button with Tooltip",
    description="This interface showcases a button with a tooltip.",
    fn=button_click,
    inputs=[
        # If X and Y are not set, the tip will be center-top aligned with the button
        buttontip_component(
            tooltip="Tooltip Text",
            tooltip_color="white",  # Custom color
            tooltip_background_color="red",
            value="Top Button"
        ),
        # Change X, Y values to position the tooltip
        buttontip_component(
            tooltip="Tooltip Text",
            tooltip_color="white",  # Custom color
            tooltip_background_color="green",
            x=50,  # No horizontal offset
            y=-20,  # Below the button
            value="Bottom Button"
        )
    ],
    outputs="text",
)


if __name__ == "__main__":
    demo.launch()

```

## `buttontip_component`

### Initialization

<table>
<thead>
<tr>
<th align="left">name</th>
<th align="left" style="width: 25%;">type</th>
<th align="left">default</th>
<th align="left">description</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left"><code>value</code></td>
<td align="left" style="width: 25%;">

```python
str | Callable
```

</td>
<td align="left"><code>"Run"</code></td>
<td align="left">Default text for the button to display. If callable, the function will be called whenever the app loads to set the initial value of the component.</td>
</tr>

<tr>
<td align="left"><code>every</code></td>
<td align="left" style="width: 25%;">

```python
Timer | float | None
```

</td>
<td align="left"><code>None</code></td>
<td align="left">Continously calls `value` to recalculate it if `value` is a function (has no effect otherwise). Can provide a Timer whose tick resets `value`, or a float that provides the regular interval for the reset Timer.</td>
</tr>

<tr>
<td align="left"><code>inputs</code></td>
<td align="left" style="width: 25%;">

```python
Component | Sequence[Component] | set[Component] | None
```

</td>
<td align="left"><code>None</code></td>
<td align="left">Components that are used as inputs to calculate `value` if `value` is a function (has no effect otherwise). `value` is recalculated any time the inputs change.</td>
</tr>

<tr>
<td align="left"><code>variant</code></td>
<td align="left" style="width: 25%;">

```python
Literal["primary", "secondary", "stop"]
```

</td>
<td align="left"><code>"secondary"</code></td>
<td align="left">'primary' for main call-to-action, 'secondary' for a more subdued style, 'stop' for a stop button.</td>
</tr>

<tr>
<td align="left"><code>size</code></td>
<td align="left" style="width: 25%;">

```python
Literal["sm", "lg"] | None
```

</td>
<td align="left"><code>None</code></td>
<td align="left">Size of the button. Can be "sm" or "lg".</td>
</tr>

<tr>
<td align="left"><code>icon</code></td>
<td align="left" style="width: 25%;">

```python
str | None
```

</td>
<td align="left"><code>None</code></td>
<td align="left">URL or path to the icon file to display within the button. If None, no icon will be displayed.</td>
</tr>

<tr>
<td align="left"><code>link</code></td>
<td align="left" style="width: 25%;">

```python
str | None
```

</td>
<td align="left"><code>None</code></td>
<td align="left">URL to open when the button is clicked. If None, no link will be used.</td>
</tr>

<tr>
<td align="left"><code>visible</code></td>
<td align="left" style="width: 25%;">

```python
bool
```

</td>
<td align="left"><code>True</code></td>
<td align="left">If False, component will be hidden.</td>
</tr>

<tr>
<td align="left"><code>interactive</code></td>
<td align="left" style="width: 25%;">

```python
bool
```

</td>
<td align="left"><code>True</code></td>
<td align="left">If False, the ButtonTip will be in a disabled state.</td>
</tr>

<tr>
<td align="left"><code>elem_id</code></td>
<td align="left" style="width: 25%;">

```python
str | None
```

</td>
<td align="left"><code>None</code></td>
<td align="left">An optional string that is assigned as the id of this component in the HTML DOM. Can be used for targeting CSS styles.</td>
</tr>

<tr>
<td align="left"><code>elem_classes</code></td>
<td align="left" style="width: 25%;">

```python
list[str] | str | None
```

</td>
<td align="left"><code>None</code></td>
<td align="left">An optional list of strings that are assigned as the classes of this component in the HTML DOM. Can be used for targeting CSS styles.</td>
</tr>

<tr>
<td align="left"><code>render</code></td>
<td align="left" style="width: 25%;">

```python
bool
```

</td>
<td align="left"><code>True</code></td>
<td align="left">If False, component will not render be rendered in the Blocks context. Should be used if the intention is to assign event listeners now but render the component later.</td>
</tr>

<tr>
<td align="left"><code>key</code></td>
<td align="left" style="width: 25%;">

```python
int | str | None
```

</td>
<td align="left"><code>None</code></td>
<td align="left">if assigned, will be used to assume identity across a re-render. Components that have the same key across a re-render will have their value preserved.</td>
</tr>

<tr>
<td align="left"><code>scale</code></td>
<td align="left" style="width: 25%;">

```python
int | None
```

</td>
<td align="left"><code>None</code></td>
<td align="left">relative size compared to adjacent Components. For example if Components A and B are in a Row, and A has scale=2, and B has scale=1, A will be twice as wide as B. Should be an integer. scale applies in Rows, and to top-level Components in Blocks where fill_height=True.</td>
</tr>

<tr>
<td align="left"><code>min_width</code></td>
<td align="left" style="width: 25%;">

```python
int | None
```

</td>
<td align="left"><code>None</code></td>
<td align="left">minimum pixel width, will wrap if not sufficient screen space to satisfy this value. If a certain scale value results in this Component being narrower than min_width, the min_width parameter will be respected first.</td>
</tr>

<tr>
<td align="left"><code>tooltip</code></td>
<td align="left" style="width: 25%;">

```python
str
```

</td>
<td align="left"><code>None</code></td>
<td align="left">None</td>
</tr>

<tr>
<td align="left"><code>tooltip_color</code></td>
<td align="left" style="width: 25%;">

```python
str
```

</td>
<td align="left"><code>"#fff"</code></td>
<td align="left">None</td>
</tr>

<tr>
<td align="left"><code>tooltip_background_color</code></td>
<td align="left" style="width: 25%;">

```python
str
```

</td>
<td align="left"><code>"#000"</code></td>
<td align="left">None</td>
</tr>

<tr>
<td align="left"><code>x</code></td>
<td align="left" style="width: 25%;">

```python
int
```

</td>
<td align="left"><code>None</code></td>
<td align="left">Horizontal offset of the tooltip from the button.</td>
</tr>

<tr>
<td align="left"><code>y</code></td>
<td align="left" style="width: 25%;">

```python
int
```

</td>
<td align="left"><code>None</code></td>
<td align="left">Vertical offset of the tooltip from the button.</td>
</tr>
</tbody></table>


### Events

| name | description |
|:-----|:------------|
| `click` | Triggered when the buttontip_component is clicked. |



### User function

The impact on the users predict function varies depending on whether the component is used as an input or output for an event (or both).

- When used as an Input, the component only impacts the input signature of the user function.
- When used as an output, the component only impacts the return signature of the user function.

The code snippet below is accurate in cases where the component is used as both an input and an output.

- **As output:** Is passed, (Rarely used) the `str` corresponding to the button label when the button is clicked.
- **As input:** Should return, string corresponding to the button label.

 ```python
 def predict(
     value: str | None
 ) -> str | None:
     return value
 ```
 
