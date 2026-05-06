# HTML Image Test

Test cases for HTML \`<img>\` tag rendering in the editor.

## Basic Image

![Cool parrot](cstore-file:///Users/jlong/Documents/ContextStore/personal-docs-space/Scratch/cool-parrot.gif "Cool parrot")

## Right-Aligned Image

![Batman thinking](cstore-file:///Users/jlong/Documents/ContextStore/personal-docs-space/Scratch/batman-thinking.gif "Batman thinking")

This paragraph should wrap around the image which is floated to the right side. The image has an explicit width of 160 pixels. Text continues to flow normally on the left side of the image. Adding more text here so we can see the wrapping behavior clearly.

## Left-Aligned Image

![Business high five](cstore-file:///Users/jlong/Documents/ContextStore/personal-docs-space/Scratch/business-high-five.gif "Business high five")

This paragraph should wrap around the image which is floated to the left side. The image has an explicit width of 160 pixels. Text continues to flow normally on the right side of the image. Adding more text here so we can see the wrapping behavior clearly.

## Center-Aligned Image

![ContextStore logo](cstore-file:///Users/jlong/Documents/ContextStore/personal-docs-space/Images/contextstore.png "ContextStore logo")

## Width and Height

![Arnold](cstore-file:///Users/jlong/Documents/ContextStore/personal-docs-space/Images/arnold-do-it-now.jpg "Arnold")

## Void Form (No Trailing Slash)

![Approved](cstore-file:///Users/jlong/Documents/ContextStore/personal-docs-space/Images/approved.png "Approved")

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
