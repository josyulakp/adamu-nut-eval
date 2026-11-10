# ADAM-U nut pick: interactive evaluation page

Static front end for evaluating trained robot policies in simulation. Drag the nut and the target on the table
map, choose a policy (Diffusion Policy, ACT, DP + DSRL, Touch in the Wild, DexScrew) and a condition, and press
**Pick**. The episode runs in MuJoCo on a Hugging Face Space and streams back to this page: the robot in 3D, the
camera image the policy saw and, for the tactile policies, the FlexiTac pads.

* Models: [huggingface.co/josyula/adamu-nut-policies](https://huggingface.co/josyula/adamu-nut-policies)
* Model server: [huggingface.co/spaces/josyula/adamu-nut-eval](https://huggingface.co/spaces/josyula/adamu-nut-eval)

The page is plain HTML with Three.js from a CDN; there is no build step. The server URL is the
`<meta name="eval-api">` tag in `index.html`, and `?api=<url>` on the page URL overrides it (for example to point
at a server running on your own machine: `?api=http://localhost:8770`).

`scene_*.json` and `meshes_*.bin` are the robot and table geometry, exported from the MuJoCo scenes.
