# HTML Image Test

Test cases for HTML \`<img>\` tag rendering in the editor.

## Basic HTTP Image

<img src="https://picsum.photos/300/200" alt="Random photo" />

## Right-Aligned Image

<img src="https://github.githubassets.com/favicons/favicon.png" align="right" width="64" />

This paragraph should wrap around the GitHub favicon which is floated to the right side. The image has an explicit width of 64 pixels. Text continues to flow normally on the left side of the image.

## Left-Aligned Image

<img src="https://github.githubassets.com/favicons/favicon.png" align="left" width="64" />

This paragraph should wrap around the GitHub favicon which is floated to the left side. The image has an explicit width of 64 pixels. Text continues to flow normally on the right side of the image.

## Center-Aligned Image

<img src="https://picsum.photos/400/150" align="center" alt="Centered photo" />

## Width and Height

<img src="https://picsum.photos/600/400" width="200" height="133" alt="Resized photo" />

## Void Form (No Trailing Slash)

<img src="https://picsum.photos/150/150" alt="Void form test">

## Relative Path (Local Image)

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
