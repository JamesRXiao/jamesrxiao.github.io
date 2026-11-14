---
title: "FormCakes (Formlabs Hackathon 2026)"
excerpt: "Building a pancake batter injection molding machine for Formlabs IAP Hackathon 2026."
date: 2026-02-01
layout: single
header:
  teaser: /assets/images/projects/formcakes/cover.png
teaser_position: "50% 45%"
toc: false

gallery_1:
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635760/Screenshot_2026-11-14_004859.png
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635760/Screenshot_2026-11-14_004859.png
    alt: "cad"
    title: "CAD"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635756/IMG_2891.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635756/IMG_2891.heic
    alt: "miters"
    title: "Working in MITERS"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635759/IMG_2911.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635759/IMG_2911.heic
    alt: "miters"

gallery_2:
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635755/IMG_2879.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635755/IMG_2879.heic
    alt: "miters"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635756/IMG_2885.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635756/IMG_2885.heic
    alt: "miters"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635757/IMG_2893.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635757/IMG_2893.heic
    alt: "demo"

gallery_3:
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635760/Screenshot_2026-11-14_004849.png
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635760/Screenshot_2026-11-14_004849.png
    alt: "operation"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635758/IMG_2907.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635758/IMG_2907.heic
    alt: "benchy"
    title: "world's first pancake benchy"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635906/IMG_2902.jpg
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635906/IMG_2902.jpg
    alt: "benchy"
  - image_path: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635758/IMG_2908.heic
    url: https://res.cloudinary.com/uzoen9fy/image/upload/v1794635758/IMG_2908.heic
    alt: "benchy"
---

I did this project with 2 of my friends, Vaughn Khouri and John Xu, for the Formlabs IAP Hackathon in January 2025. Our goal was to design and build an injection molding machine - but for pancakes. Completed in under 48 hours, our machine injected pancake batter in a Benchy mold, heated the mold, and automatically ejected the pancake Benchy onto a plate. 

I was responsible for the electronics and firmware development for this project. 

The aluminum mold was heated with several PTC heating elements, and both halves were actuated by stepper-controlled ball screws. A third stepper motor controlled batter injection.

{% include gallery id="gallery_1" class="breakout gallery-equal" height="225px" shift="4vw" total_width="1000px"%}


Our microcontroller was a Raspberry Pi Pico 2W, running a state machine that handled all stepper motors, relays to control the 120VAC PTC heaters, limit switches for calibration, and temperature sensing (which we ultimately didn't use). 

{% include gallery id="gallery_2" class="breakout gallery-equal" height="250px" shift="4vw" total_width="1000px"%}


In the last 12 hours, we realized we could use an solenoid and compressed air to eject the pancake out the mold instead of ejection pins in a standard injection molding machine. It made for quite an exciting ending to our print :D

After just a bit of tuning with batter volume and heating time, we were able to get it working! At the end of the day, we were holding the world's first pancake Benchy.

{% include gallery id="gallery_3" class="breakout gallery-equal" height="350px" shift="4vw" total_width="1000px"%}

Witness our live reactions to the first successful print!:

<figure style="max-width: 800px; margin: 2em auto;">
  <video controls preload="metadata" playsinline
         poster="https://res.cloudinary.com/uzoen9fy/video/upload/v1794635762/IMG_7115-00.05.07.340-00.05.59.635.jpg"
         style="width: 100%; border-radius: 8px;">
    <source src="https://res.cloudinary.com/uzoen9fy/video/upload/v1794635762/IMG_7115-00.05.07.340-00.05.59.635.webm" type="video/webm">
    <source src="https://res.cloudinary.com/uzoen9fy/video/upload/v1794635762/IMG_7115-00.05.07.340-00.05.59.635.mov" type="video/mov">
  </video>
</figure>