Resources

Course Link
https://youtu.be/rxTb9ys834w

Original Website
https://bokoko33.me/

Full Source Code
https://github.com/andrewwoan/abigail-bloom-portolio-bokoko33
(Blender file with paid option has been removed to prevent copying)

Fix Blender Shading on Joined Objects
https://blender.stackexchange.com/questions/159218/shade-smooth-and-auto-smooth-problem-when-combining-objects

Design Patterns and Refactoring
https://refactoring.guru/design-patterns

Responsive GSAP with Window Match Media API
https://greensock.com/forums/topic/25629-triggering-different-timelines-at-different-breakpoints-with-matchmedia/

Add empty space at end of GSAP timeline
https://greensock.com/forums/topic/8433-how-to-add-time-at-the-end-of-a-timeline/

----- Zooming a camera with GSAP -----
1.) Set an initial zoomValue inside an object (which is the default camera zoom), call it whatever you want by the way
this.zoom = {
zoomValue: this.camera.perspectiveCamera.zoom,
};

2.) Tween that zoom's object's value with GSAP,
timeline.to(this.zoom, {
zoomValue: 4,
});

3.) Update the camera's zoom and set it equal to that zoomValue that we are updating with GSAP's onUpdate built in functionality.
timeline.to(this.zoom, {
zoomValue: 4,
onUpdate: () => {
this.camera.perspectiveCamera.zoom = this.zoom.zoomValue;
this.camera.perspectiveCamera.updateProjectionMatrix();
},
});

FAQs

Why did I leave in bad code?
It’s much faster to write and the video was getting really long. Usually “bad code” is easier to write initially but more difficult to change later on. “Good code” is usually the opposite, takes longer to write initially but easier to change in the long run. In any case, the logic and conceptual parts on what to do and consider are still the same.

Really really bad code is when the code starts causing performance issues.

Bug Fixes (if necessary)

The GumRoad source files are always updated with these changes!!

Change first move timeline to use fromTo so GSAP knows to go back to 0,0,0

this.firstMoveTimeline.fromTo(
this.room.position,
{ x: 0, y: 0, z: 0 },
{
x: () => {
return this.sizes.width \* 0.0014;
},
}
);
Use this in Controls.js to determine if smooth scroll should be set or not, otherwise the progress bar will bug out on Mobile devices

export default class Controls {
constructor() {
//…. Other stuff

if (!/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(
navigator.userAgent
)
) {
this.setSmoothScroll();
}

}

Next Steps

Learn More About Three.js and join an AMAZING Creative Developer Community:
https://threejs-journey.xyz/
Create your own amazing awwwards site.
I’d love to see what you make, feel free to tag me:
https://twitter.com/AndrewWoan
https://www.instagram.com/andrewwoan/
