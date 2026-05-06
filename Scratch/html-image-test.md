# HTML Image Test

Test cases for HTML \`<img>\` tag rendering in the editor.

## Basic Image

<img src="cool-parrot.gif" alt="Cool parrot" />

## Right-Aligned Image

<img src="batman-thinking.gif" align="right" width="160" alt="Batman thinking" />

This paragraph should wrap around the image which is floated to the right side. The image has an explicit width of 160 pixels. Text continues to flow normally on the left side of the image. Adding more text here so we can see the wrapping behavior clearly.

## Left-Aligned Image

<img src="business-high-five.gif" align="left" width="160" alt="Business high five" />

This paragraph should wrap around the image which is floated to the left side. The image has an explicit width of 160 pixels. Text continues to flow normally on the right side of the image. Adding more text here so we can see the wrapping behavior clearly.

## Center-Aligned Image

<img src="../Images/contextstore.png" align="center" width="200" alt="ContextStore logo" />

## Width and Height

<img src="../Images/arnold-do-it-now.jpg" width="200" height="150" alt="Arnold" />

## Void Form (No Trailing Slash)

<img src="../Images/approved.png" alt="Approved" width="64">

## Remote URL

<img src="../Images/contextstore.png" width="128" alt="ContextStore logo" />

## Security: Blocked Sources

These should show "Blocked image" indicators, not render:

<img src="javascript:alert('xss')" alt="JS injection" />

<img src="data:image/png;base64,iVBOR" alt="Data URI" />

## Fallback: Broken Image

<img src="https://example.com/nonexistent-image-12345.png" alt="This image does not exist" />

## Preserved Attributes

This image has extra attributes that should roundtrip losslessly:

<img src="https://picsum.photos/200/200" class="hero-image" id="main-photo" data-caption="A test image" title="Hover text" style="border: 1px solid red" />
