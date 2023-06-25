---
Tags:
- ❔類型/⭐精選/📖圖文教材
- ❔專業領域/🧠AI
---
https://toyxyz.gumroad.com/l/ciojz?layout=profile&recommended_by=library
![](https://public-files.gumroad.com/7cfq68mxf3upfrtgfcq6zjexgtr9)
-Blender version 3.5 or higher is required.-

[Download —](https://www.blender.org/download/) [blender.org](http://blender.org/)

[Guide : https://youtu.be/f1Oc5JaeZiw](https://youtu.be/f1Oc5JaeZiw)

  

Character bones that look like Openpose for blender _Ver_9 Depth+Canny+Landmark+MediaPipeFace+finger

Added extra limbs.Extra limbs are useful for generating monster characters.

![](https://public-files.gumroad.com/wb38oxil721gb6xxyf0u5629bsl6)

![](https://public-files.gumroad.com/ipppqj6k28xo4evg93hnl1tq5bkj)

Open pose images with extra limbs are stored in a separate folder 'openpose_full_Extra_Limb'.

![](https://public-files.gumroad.com/tq45ngbpbcc8837zyozb9hgixye7)

If you don't see the extra limbs, enable the Openpose_Extralimb collection in the outliner.

![](https://public-files.gumroad.com/4njcl9k782quko1md0rifu0vlkeg)

  

Additional limbs are controlled by vertices rather than rigs for editing ease. Extruding vertices adds joints. The hands can be controlled using a rig.

![](https://public-files.gumroad.com/osfbzhk8k1f707btb3m3tx77x4tl)

![](https://public-files.gumroad.com/xc5geut9k4iuoe1u6sttrkzwaham)

Wire mode added. Enabling it makes it easier to adjust the rig. It is automatically disabled when rendering.

  

![](https://public-files.gumroad.com/pgqbeu969ngta8hjbjk4gsv36o2b)

  

---

Character bones that look like Openpose for blender _Ver_8.1 Depth+Canny+Landmark+MediaPipeFace+finger

Added line art support and fixed some bugs.

![](https://public-files.gumroad.com/xh8jnlmiklzq0jssstwrqiezsre8)

  

---

Character bones that look like Openpose for blender _Ver_8 Depth+Canny+Landmark+MediaPipeFace+finger

Added support for new open poses (finger + face) updated in ControlNet v1.1.

ControlNet v1.1 : [lllyasviel/ControlNet-v1-1 at main (](https://huggingface.co/lllyasviel/ControlNet-v1-1/tree/main)[huggingface.co](http://huggingface.co/)[)](https://huggingface.co/lllyasviel/ControlNet-v1-1/tree/main)

![](https://public-files.gumroad.com/nzh8ftonr133orlz6sq2qj7zztta)

Dot Size; The size of the finger joint blue dots.

Line_thickness : Line thickness

Auto_size: Automatically adjust thickness according to camera distance.

Auto_Size_mult: auto thickness adjustment multiply

Emission: brightness adjustment

![](https://public-files.gumroad.com/1vknzm0uwh10rsbb9dh1x3ncmf05)

Hands, faces, and combined images are each stored in separate folders.

![](https://public-files.gumroad.com/9r0wrr0dez4qdtsmlefoo7bj1laq)

The location of the parameters of the open pose body has been changed from object properties to modifiers.

![](https://public-files.gumroad.com/9mqe0xvwvpozczohkhrxtnnf1663)

  

---

Added MediaPipeFace controlnet model support.

Download the appropriate controlnet model file and place it in your extension's model folder.

[CrucibleAI/ControlNetMediaPipeFace · Hugging Face](https://huggingface.co/CrucibleAI/ControlNetMediaPipeFace)

![](https://public-files.gumroad.com/je822tdc9m8ld1ynmsoznaz850kk)

![](https://public-files.gumroad.com/11ml1zoig9nplx3qz4k0sj9gzzfu)

Hide_Iris_Auto: Automatically hides the iris when the eyes are closed.

Hide_Iris_Left/Right : Hides left/right iris.

Iris_Size : Adjust the iris size.

Auto_Thick: Automatically adjusts the line thickness according to the camera distance.

Thick_multi : Adjust the thickness of the line.

Jaw_Size: Adjust the length of the jaw.

Face_width : Adjusts the width of the face.

![](https://public-files.gumroad.com/9dqzwt0vbfjkdfg86r4690s5cs9i)

  

---

Character bones that look like Openpose for blender _Ver__6 Depth + Canny + Landmark

Added landmarks for facial landmark controlnet.

Face landmark controlnet model : [georgefen/Face-Landmark-ControlNet at main (](https://huggingface.co/georgefen/Face-Landmark-ControlNet/tree/main/models)[huggingface.co](http://huggingface.co/)[)](https://huggingface.co/georgefen/Face-Landmark-ControlNet/tree/main/models)

![](https://public-files.gumroad.com/4dyxw0izbq1g2vnyvsve001yxq2h)

The combination of Canny and Landmark allows more precise control of facial expressions and shapes.

![](https://public-files.gumroad.com/3ltcwpm0mh1zvjj0re6575vn8tv7)

  

  

You can find it in the Landmark collection.

ShowFaceMesh : show/hide face mesh

Show_Extra_side : Show extra dots to assist the side of the face. Dots displayed in side view. It is used when the face turns more than intended.

![](https://public-files.gumroad.com/r3nz66md0nnfm0evpjxgm30dbngy)

DotSize : Dot size

Inflat_outline: Inflate the facial outline dots.

Inflat_face: Inflate the face (eyes, nose and mouth) dots.

Jaw_size : adjust jaw size. Useful for creating realistic human images.

![](https://public-files.gumroad.com/fjf5qm7yhqjclr4fxgvvz25s3lfq)

Auto_dot_size : Automatically adjust the dot size according to the distance from the camera On/Off

  

![](https://public-files.gumroad.com/fnplly9jefnnv5l92hz78t34i0jz)

![](https://public-files.gumroad.com/3shmmz1bh3smb2suhsuz8hwwslf8)

It is no longer necessary to render each ControlNet image separately. When F12 or Render/Render image button is pressed, a MultiControlnet folder is automatically created in the path where the blend file is located, and each controlnet image is saved separately. If you want to avoid overwriting the image, change the frame in the timeline each time you render.

![](https://public-files.gumroad.com/mzoeevbiqbeojm0b17cn90hhd5dx)

  

  
--------------------------------------------------------------------------------------------------------

Character bones that look like Openpose for blender _Ver__5 Depth + Canny

Faces were added in v5. To be precise, eyes, eyebrows, mouth and tongue were added.

![](https://public-files.gumroad.com/0o85e333lflx8xd0w9uk9rrfxufu)

In order to obtain the desired result, you must properly adjust the weight, Guidance Start, and Guidance End, and use the appropriate Prompt.

![](https://public-files.gumroad.com/5yrz9lgrfa47wba4c6bbi26vtojf)

![](https://public-files.gumroad.com/sy93sagsvnlk1wlcq60l37vw0hxq)

Because it was designed for 2D characters, it doesn't work well with realistic models. You may need to adjust the size and position of the eyes and mouth.

![](https://public-files.gumroad.com/3zue48l0q7acaz3n7tvapmgocm0l)

  

---

Character bones that look like Openpose for blender _Ver__4.7 Depth + Canny

The toes can now move individually.

  

![](https://public-files.gumroad.com/cehgpwm111siceuggshamtvy3ag1)

  

---

Character bones that look like Openpose for blender _Ver__4.6 Depth + Canny

I checked the file and found that the show head was missing. I added it again, so please download the latest version.  

---

  

Character bones that look like Openpose for blender _Ver__4.5 Depth + Canny

In ver_4.5, T2I-Adapter's keypose bone was added.

![](https://public-files.gumroad.com/i9kflvs4mq0q0eoelho990rff8yo)

Hide and show whatever you want in the outliner's collection. Main_ring is an adjustment rig, and Keypose_bone and Openpose_bone are corresponding bones respectively.

![](https://public-files.gumroad.com/6cdf9oplx9c8p5g0s66qcfwwgz1s)

As with the open pose bone, you can adjust the bone's thickness, brightness, and automatic thickness adjustment in the custom properties of the key pose bone.

![](https://public-files.gumroad.com/7o9oab9uwtjwmbqjkja16et2wvra)

  

---

Character bones that look like Openpose for blender _Ver__4 Depth + Canny

The feet have now been added.

![](https://public-files.gumroad.com/oh5y4o7bkmcmxjkx35wqss18xjen)

For toes, Canny works a bit better than Depth.

![](https://public-files.gumroad.com/5v3l9d70ura0518ocr7n32zszazk)

Depth and Canny have been merged into one file.

Hide the other Collections in the Outliner except the one you want between Depth and Canny.

![](https://public-files.gumroad.com/qpomn4y4bvu6g1onzk7h5kb3j7pa)

  

---

Character bones that look like Openpose for blender _Ver__3.5 Depth + Canny

![](https://public-files.gumroad.com/z5ym9vvfi5j0z8rur9lv8gr8l3kq)

For Canny version, the preprocessor must be set to Canny.

Unlike depth, setting it to None won't work.

In the outliner, the Canny collection includes hands and a white background for Canny. Hide and show as needed.

  

![](https://public-files.gumroad.com/lm601m8o8tr1p3gof2fmtmu3x1hb)

The line thickness of the hand can be changed through Thickness in Solidify in the modifier list.

  

![](https://public-files.gumroad.com/k8ebv575xq5ckogz0dsefix3a1dp)

  

---

Character bones that look like Openpose for blender _Ver__3

In Ver 3, a hand mesh was added. It is possible to adjust the fingers more precisely by rendering the hand mesh depth and open pose bone images separately and inputting them to Multi-ControlNet.

![](https://public-files.gumroad.com/hd8hlkfxtrih2gblw0etsvighijs)

![](https://public-files.gumroad.com/ie4yejdd11itsl0mplh89l6agdi3)

![](https://public-files.gumroad.com/5t4gp9gi5efc4w9reii7ozpr259e)

See this video on how to render a depth image in Blender.

  

---

Character bones that look like Openpose for blender _Ver__2

In Ver_2, thickness adjustment function was added.

When using the ControlNet Openpose model, the line and dot thickness should be constant regardless of distance to obtain an optimal image.

In the image below, compared to the upper row with a constant thickness, the lower row with different thickness starts to break the pose from the middle.

![](https://public-files.gumroad.com/07hm49gcfigsmz1eszpgb6fod7ca)

In the viewport, select "OpenBone_body_v2", a colored mesh, and the adjustment options are available in the object properties.

-Alpha: Adjust the transparency of the skeleton. 1 is completely transparent.

-Auto_Size_multi: Multiplier for auto-adjusting bone thickness.

Distance between Thickness_Handle and bone / Auto_Size_multi = Auto thickness

-Auto_size : Use automatic bone thickness adjustment. 0 : disable, 1 : enable

- Emission: Bone brightness adjustment

-Show_Head : Show or hide the head.

-Thickness: Bone thickness automatically adjusted when Auto_size is enabled.

-Thickness_Ball: Adjust the thickness of the spheres located at the joint.

-Thickness_Head: Adjusts only the thickness of the bones located on the head.

-Thickness_Second : Adjust overall bone thickness

![](https://public-files.gumroad.com/aj6p2m6k5r9qrxmn7pnr4volchrt)

  

![](https://public-files.gumroad.com/f47j60cmjnmmxncbu67ok1vj9iay)

If Auto_size is set to 1, the thickness of the bone is automatically adjusted according to the distance between the Thickness_Handle and the open pose bone. Thickness_Handle is constrained to Camera.

  

![](https://public-files.gumroad.com/nmqijupn025a9egk0zxmjjdtelx6)

  

![](https://public-files.gumroad.com/1uvzyw4vh2o0p4wdu9b16f86kwxj)

![](https://public-files.gumroad.com/lug7yg3ww42p0okpuu9j40poxce1)

![](https://public-files.gumroad.com/86nfbcg2v2us5ka902crcb4fz535)

  

  

  

  

---

  

Character bones that just look like Openpose.

It is designed for use with ControlNet Pose2Image (Openpose).

[Mikubill/sd-webui-controlnet: WebUI extension for ControlNet (](https://github.com/Mikubill/sd-webui-controlnet)[github.com](http://github.com/)[)](https://github.com/Mikubill/sd-webui-controlnet)

You can use it after setting Preprocessor to none and Model to Oenpose.

Made using Autorig-Pro. Install rig_tools_3.67.12.zip if you don't have this Addon. You can use it without it, but then you cannot change rig properties like the FK<->IK switch.

![](https://public-files.gumroad.com/n8b37ov4w7m7qdm45y8ylpcofway)

![](https://public-files.gumroad.com/asrb8xcrdq1eropnm7lisv1h6f7y)

  

You can adjust the brightness and transparency of the skeleton in the object properties.

  

![](https://public-files.gumroad.com/pxns9spborrn0q1s1b2h1gk1pgbo)

  

  
