# cat-subject-focus

Evaluates how well photographic focus serves a cat as the subject of an image. Scores the photograph from 0 to 1 by assessing focal separation between the cat and its surroundings, the internal clarity of the cat's physical features, and whether focus grants the cat visual command over the entire scene.

## Input

The function accepts a single required field:

| Field | Type | Required | Description |
|---|---|---|---|
| `photograph` | `image` | Yes | A photograph containing a cat. The image may come from any source — a professional camera, a smartphone, a surveillance camera, or any other device. The cat may be in any position, pose, or state of motion. The scene may be simple or cluttered, indoors or outdoors, well-lit or dim. |

## Output

A scalar score between **0** and **1**.

- **Scores near 1.0** indicate that the cat is the sharpest element in the image, its features are crisply defined, and it commands the scene as the undeniable subject.
- **Scores near 0.5** indicate mixed results — the cat may be partially sharp but shares focus with its surroundings, or its features are only partially resolved, or it does not fully dominate the scene.
- **Scores near 0.0** indicate that the cat is out of focus, motion-blurred, or softer than its surroundings, with poorly defined features and no visual authority as the subject.

## What It Evaluates

The function evaluates three distinct qualities, each contributing to the final score:

### 1. Focal Separation

The relationship between the sharpness of the cat and the sharpness of its surroundings. This quality asks whether focus creates a visual hierarchy — whether the cat is rendered more crisply than the background, foreground, and nearby objects, drawing the viewer's eye toward it. A cat in sharp focus against a softened background demonstrates strong focal separation. A cat that shares equal sharpness with everything around it, or appears softer than its surroundings, demonstrates weak or failed focal separation. This is not a demand for dramatic bokeh or shallow depth of field — it is an assessment of whether any meaningful difference in sharpness exists that prioritizes the cat.

### 2. Feature Definition

The internal clarity of the cat's own physical form. Even when a cat is the sharpest thing in the frame, this quality asks whether its features are actually resolved: whether the eyes are sharp and legible, the fur shows visible texture and pattern, the ears have crisp edges, and the body contour is well-delineated. Motion blur, excessive distance, or insufficient resolution can rob a cat of its feature definition, reducing it from a recognizable portrait to an indistinct shape. This quality distinguishes between a cat that is merely located within the focal plane and a cat whose form is truly rendered with clarity.

### 3. Visual Authority

The holistic effect of focus across the entire photograph. This quality asks whether the cat commands the scene as the undeniable subject — whether a viewer would immediately understand "this is a picture of a cat" rather than "this is a picture of a scene that happens to contain a cat." Visual authority accounts for competing elements (other animals, human faces, prominent objects), the cat's prominence within the frame, and whether the overall focal emphasis conspires to make the cat the thing that matters most. A cat may be sharp and well-defined yet still lack visual authority if it occupies a small corner of a vast, equally detailed scene.

## Use Cases

- **Pet adoption platforms** — Surface the strongest, most subject-focused portraits of cats awaiting homes, helping each cat make a compelling first impression on potential adopters.
- **Social media and content curation** — Distinguish cat photos where the cat leaps off the screen from those where it is lost in visual noise, serving as a quality signal for ranking and recommendation systems.
- **Photography workflows** — Help photographers sort through large shoots to identify the keepers: frames where focus landed precisely on the cat rather than drifting to the background.
- **Veterinary and animal welfare documentation** — Flag images that lack the internal clarity needed to see a cat's distinguishing physical characteristics for identification or medical records.

## Important Notes

- This function is **not a measurement of absolute technical sharpness or pixel-level resolution**. A modest-resolution image where the cat emerges clearly from its surroundings can score higher than a technically perfect image where the cat has no special visual standing.
- The function expects that **a cat is present** in the photograph. It evaluates how well focus serves that cat as the subject — it does not detect whether a cat exists.
- All three evaluation qualities contribute to the final score. A photograph must succeed across focal separation, feature definition, and visual authority to achieve the highest scores.
