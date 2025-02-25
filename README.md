# Tales of Vin: an interactive virtual world inspired by van Gogh

**Imagine stepping inside a Vincent van Gogh painting — not just admiring it from afar, but diving into the stories, emotions, and relationships that shaped his art. This project transports you into an interactive virtual world where art comes to life, and every brushstroke tells a story. Through interactive levels and guided quests, you'll explore his iconic masterpieces while uncovering the lesser-known aspects of his troubled life, experiencing a captivating journey of color, sound and narrative. It's not just a visual experience; it's an intimate dialogue between the user and the artist, where technology and creativity merge to offer a new way of engaging with art. A unique opportunity to discover and immerse yourself in the tales Vincent himself told through his art work.**

### **Index**
- [Overview](#overview)
- [Concept](#installazione)
- [Prototyping](#uso)
- [Architettura](#architettura)
- [Risultati](#risultati)
- [Conclusioni](#conclusioni)
- [Licenza](#licenza)

***
### **Overview**
`virtual reality`, `digital narrative`, `interactivity`, `videogame`,`accessibility of art`, `Van Gogh`

![](https://github.com/gretablt/Tales-of-Vin/Samples/VanGoghMilano.jpg)
> Van Gogh: The Immersive Experience, Milano 2023.

This project was inspired by the recent popularity of immersive Van Gogh exhibitions that use projections to animate his artwork in large, visually captivating spaces. While these experiences are widely celebrated for their appeal, they often lack depth, offering only a brief, surface-level connection to the artist’s work. My goal is to create an experience that combines virtual reality and digital art to make Van Gogh’s work accessible and educational for new audiences, especially those who may feel distanced from traditional art settings. Using 3D modeling, interactivity, and immersive environments, this project aims to offer a meaningful, engaging way to experience Van Gogh’s legacy—inviting a younger, tech-savvy audience to connect with art in a fresh and personal way.

### **Concept**
Vincent’s Tales is an immersive virtual experience that brings Vincent van Gogh’s art and life into an interactive digital world. Rather than simply replicating museum spaces, the project reinterprets his works in a dynamic 3D environment, making them more engaging and accessible.

Through interactive storytelling and quests, users explore Van Gogh’s world firsthand. Painted landscapes become explorable settings, portraits turn into avatars, and iconic elements like sunflowers become collectible objects. The journey begins in the wheat fields near Arles, guiding players toward the town, where they meet figures like Gauguin, visit the Yellow House, and uncover stories about Van Gogh’s daily life.

Unlike traditional virtual museums, which often replicate physical spaces without enhancing engagement, "Vincent’s Tales" embraces digital art’s full potential. A faithful 3D reproduction of paintings alone cannot match the experience of seeing them in person. Instead, this project reinterprets Van Gogh’s work, integrating interactivity, storytelling, and personalization. By leveraging sound, multiplayer features, and immersive narratives, it transforms passive observation into an active, educational, and emotionally engaging journey.

***

# **Prototyping**
--> da aggiungere che la prototipazione è una demo estremamente limitata del progetto!!!

Developing the virtual experience required leveraging various software tools while overcoming technical challenges to create a highly immersive 3D environment inspired by Van Gogh’s work. The goal was to enable users to explore and interact freely, maximizing the potential of advanced 3D modeling and rendering technologies. Key tools included Blender for modeling, Substance Painter for texturing, Unity for integration into an interactive space, and Spatial for implementing augmented reality experiences. This approach surpasses traditional 360° virtual tours by offering a more engaging and interactive experience.

### 3D modeling - Blender & Substance Painter
At the core of this project is 3D modeling, essential for translating Van Gogh’s world into a digital format. Blender played a central role in creating detailed models, such as those in The Bedroom in Arles, using both polygonal modeling, which constructs objects by connecting vertices, edges, and faces, and sculpting, a technique that mimics real-world clay modeling to add intricate details. Unlike static 2D paintings, these digital 3D representations allow users to examine objects from any angle, enhancing perception of form, size, and structure.

Once the bedroom’s objects were modeled, they were resized and arranged to match Van Gogh’s original composition as accurately as possible. Given that The Bedroom was located on the ground floor of the Yellow House in Arles, the next step was modeling the exterior. Great attention was paid to architectural details—analyzing artworks depicting the house and carefully recreating elements such as cornices, window shutters, and the distinctive arched entrance.

After modeling, Substance Painter was used to create high-quality textures. This software allowed for real-time rendering with lighting effects, ensuring accurate material representation. Using digital painting techniques, dynamic brushes, projection tools, and Python-generated smart materials, textures were applied both inside the bedroom and on the Yellow House’s exterior. The texturing process involved layering properties to enhance realism: 
- base color defined the overall appearance
- metallic reflection simulated how metal surfaces interact with light
- roughness controlled surface smoothness, affecting light diffusion
- normal maps added fine details without increasing model complexity
- height maps introduced variations in surface depth for additional realism
- specular parameters determined reflectivity, crucial for materials like glass.
For instance, wooden surfaces were given high roughness and normal map values to enhance grain texture, while window glass featured high specular values and no roughness, ensuring accurate reflections. This combination of texturing techniques significantly improves the visual depth and realism of digital objects, making the virtual experience more engaging and lifelike.

### Virtual environment - Unity & Spatial Creator Toolkit
After completing the modeling and texturing phases, the project moved into the prototyping stage using Unity, a powerful and versatile game engine widely used for developing 2D and 3D interactive applications. Unity stands out for its integrated development environment, allowing creators to build, test, and refine their projects across various platforms, including PC, consoles, mobile devices, and virtual reality environments.

For this phase, Unity was combined with the Spatial Creator Toolkit, an essential resource provided by Spatial.io, a platform designed for 3D virtual experiences that enables creators to develop and share immersive social environments. Spatial.io aims to revolutionize online interaction by shifting from passive engagement to highly interactive, multiplayer virtual spaces, incorporating a virtual economy and rich user interactions.

#### Spatial Creator Toolkit
The Spatial Creator Toolkit provides a collection of tools and assets designed to simplify the development of VR and 3D environments, even for users without extensive Unity programming experience. This toolkit includes prebuilt components and user-friendly templates for scene creation, significantly streamlining the prototyping process within Unity.

However, using the Spatial toolkit comes with specific performance constraints to ensure optimal functionality within Spatial. When designing a 3D scene and importing custom assets, developers must adhere to Scene Vitals, a set of performance-related guidelines integrated into Unity's editor. Key limitations include:
- Geometry Cap: Maximum 500,000 vertices per mesh to maintain scene complexity without sacrificing performance.
- Texture Memory Limit: A maximum of 256MB of texture memory, restricting the amount of high-resolution textures used.
- Material Cap: A limit of 75 materials per scene to optimize rendering efficiency.

#### Shifting to Low-Poly for Performance Optimization
These performance constraints had a significant impact on the visual design of the prototype. The original high-detail models and textures proved incompatible with Spatial’s limits, making testing impossible. As a result, most pre-existing assets underwent substantial optimization, reducing polygon count and texture complexity. Instead of unique high-resolution textures for each object, the project adopted a single texture with different base colors, improving efficiency but reducing artistic fidelity to Van Gogh’s paintings.

This shift led to the adoption of a low-poly art style, a technique characterized by simplified 3D models with a minimal number of polygons (triangles or quads forming object surfaces). Low-poly models feature flat surfaces and sharp edges, prioritizing stylization over realism. This approach proved highly effective in:
- Reducing GPU Load: Lower polygon count decreases rendering demands, improving performance, especially on mobile devices.
- Faster Loading Times: Smaller file sizes lead to quicker asset loading and reduced storage requirements.
- Cross-Platform Compatibility: Optimized for smartphones, tablets, and web-based applications, ensuring smooth experiences across various devices.
This strategic low-poly approach was essential to maintain performance efficiency on Spatial while still delivering a visually engaging user experience.

Following asset optimization, the virtual environment was assembled using the Starter Template Main WebGL provided by the Spatial Creator Toolkit. This template includes preconfigured UI controls and avatar integration, optimized for WebGL to ensure smooth execution within web browsers. Additionally, Unity’s Universal Render Pipeline (URP) was implemented to enhance rendering quality and performance across multiple platforms.

The environment construction began with terrain modeling, using Unity's built-in Terrain system, a 3D surface that serves as the foundation for placing objects, characters, and interactive elements. This terrain was shaped based on the geography of Arles, incorporating key landmarks like the city layout, the Rhône River, and surrounding hills. Unity’s terrain system includes built-in colliders, ensuring natural physics-based interactions like object collisions and movement restrictions.

Next, 3D assets were integrated into the scene, combining custom models with prefabricated assets from the Low Poly Fantasy Valley Village pack by JustCreate. These elements—houses, windmills, bridges, fences, rocks, bushes, and street lamps—were placed using Unity’s terrain brushes, allowing for efficient object placement and density adjustments.

#### Camera system
To enhance interactivity, several core gameplay components were implemented:
- Entry Point: Defines the starting position of users when they enter the virtual space.
- Camera System: Determines how users view and navigate the environment.

For PC and mobile users, a third-person camera was set by default, providing a perspective slightly behind and above the avatar, offering a broad view of the surroundings. However, in small enclosed spaces like Van Gogh’s bedroom, this setup caused clipping issues, where the camera would unintentionally move outside walls or buildings. To address this, a first-person camera was implemented within the bedroom, allowing users to explore the space from a natural, immersive perspective.

For VR users, the first-person camera was retained, leveraging body-tracking features of VR headsets, making it feel as if the user is physically moving inside the virtual world.

### User Interface & Spatial Integration - A drastic shift in style
One of the most significant challenges in the development process was integrating an intuitive user interface while ensuring optimal performance across multiple platforms, including PC, mobile devices, and VR headsets. To achieve this, the project incorporated the UI expansion from the Spatial Creator Toolkit, which provided essential pre-built interface elements specifically designed for Spatial’s ecosystem. This integration allowed for a seamless user experience, enabling access to core features such as avatar customization, real-time chat, quest management, and NFT-based item collection.

However, the most substantial transformation during the development process was the forced transition to a low-poly aesthetic, a direct consequence of the GPU load limitations imposed by Spatial. The initial vision for the virtual experience aimed for a highly detailed and painterly environment, echoing the rich textures and expressive brushwork of Van Gogh’s paintings. However, this approach proved incompatible with Spatial’s performance constraints, making it impossible to run tests or optimize the experience for real-time interaction. To ensure smooth functionality across all platforms, including lower-end devices with limited processing power, the project had to undergo a radical visual overhaul, shifting from high-detail realism to a stylized, simplified low-poly aesthetic.

This transformation was not purely aesthetic but deeply rooted in technical necessity. The low-poly approach significantly reduced computational strain, enabling faster loading times, minimal memory usage, and a stable frame rate across mobile devices, PCs, and VR headsets. The reduced polygon count and optimized textures ensured that the scene remained lightweight and efficient, allowing users to seamlessly navigate the space without experiencing frame drops or performance hiccups. While this change marked a significant departure from the original artistic intent, it was a strategic compromise that ultimately made the experience viable within the constraints of the platform.

The interface design itself adhered to Spatial’s native UI style, maintaining a consistent look and feel within the platform while ensuring usability. The layout was carefully structured to accommodate both desktop and mobile navigation, providing users with easy access to their inventory (Backpack system), social interactions, and interactive elements. The camera settings were also customized to enhance usability, offering different viewing options depending on the environment—a third-person view for open spaces and a first-person perspective for confined areas like Van Gogh’s bedroom.

Despite the drastic stylistic shift, the low-poly adaptation ultimately enhanced the user experience by prioritizing accessibility and performance, ensuring that the virtual world remained engaging and interactive while remaining functional across all supported platforms. This shift highlights the delicate balance between artistic vision and technical feasibility, demonstrating how creative ambitions must sometimes be reshaped to fit within the constraints of emerging digital platforms.

### Interactivity and customisation
#### Ready Player Me - Avatar extension
To further enrich user immersion and customization, the Ready Player Me extension was integrated into the project. This cross-platform solution allows users to create and personalize 3D avatars, offering extensive customization options, including hairstyle, color, clothing, and facial features. One of its main advantages is the ability to generate a personalized avatar and use it seamlessly within the virtual experience.

Incorporating Ready Player Me into Spatial allowed users to import their pre-existing avatars or create a new one upon launching the experience. The integration also included built-in animations, ensuring that avatars retained a consistent and natural movement style within the environment. This feature not only enhanced personalization but also provided a cohesive and immersive user experience across platforms.

#### Movement materials and triggers
Once the 3D environment was fully designed and the core UI settings were configured, interactive mechanics were implemented to transform the space into an engaging, narrative-driven world. These interactions were made possible using the Spatial Creator Toolkit, which offers customizable interactive presets through an intuitive visual interface, eliminating the need for advanced coding skills.

The first step involved adding "movement materials", a feature that determines how different surfaces affect the avatar’s movement and sound. These were applied to three main terrain types in the virtual scene:

- Grass: Softens footstep sounds for a more natural ambiance.
- Water: Triggers a distinct splashing sound when walking through the river.
- Sand: Highlights pathways while modifying footstep sounds based on movement speed (walking vs. running).
Additionally, a teleporter was placed at the entrance of Van Gogh’s house, allowing users to seamlessly transition between outdoor and indoor environments. This feature simulated realistic spatial movement while maintaining performance efficiency.

Following this, the prototype was expanded with two key interactive elements, such as trigger events - these activate specific actions when users enter designated areas or interact with objects- and interactable elements - visual components (e.g., buttons, objects) that users can pick up, move, or interact with directly. By combining these mechanics, users could now engage in dialogues with avatars and collect or exchange objects, adding depth and meaning to their actions within the virtual world. This system was crucial in simulating interactions with historical figures, allowing players to "speak" with Van Gogh or collect artifacts tied to his artistic journey.

#### Quests and Points of interest
Quests provide structured objectives that encourage users to explore and interact with the environment. They range from simple location-based tasks, like “Explore the Gardens of Arles”—which completes automatically upon entering a designated area—to more complex challenges. An example is “Collect 11 Apples for the Next Painting”, where users gather apples scattered throughout the scene after receiving the task from the Van Gogh avatar. These mechanics promote engagement by blending exploration with interactive storytelling.

Points of Interest (POIs) serve as narrative markers, guiding users to significant locations while enriching their experience with contextual overlays containing text, images, or animations. When approaching a POI, users can view elements like Van Gogh’s Wheatfield with Crows alongside the corresponding 3D recreation, strengthening the connection between art and environment.

By combining quests and POIs, the experience balances structured engagement with organic discovery, making exploration more immersive and meaningful. Users not only navigate a visually rich space but also interact with its deeper artistic and historical context, transforming passive observation into active participation.

### Sound Design - Balancing realism and performance
The final phase of development involved integrating contextual sound design using Unity. This allowed specific environmental assets to be paired with custom audio tracks, such as:
- Flowing water near the river, with intensity varying by proximity
- Fire crackling sounds, enhancing immersion in indoor settings
- Avatar footsteps, adjusted based on the terrain.
However, attempts to assign individual audio sources to all key scene elements (e.g., rustling leaves, flickering lamps, wind effects) overloaded the system, causing preview failures due to excessive processing demands.

To optimize performance, a hybrid audio approach was implemented: a track with essential sounds (river, fire, footsteps) were directly integrated into the scene and a single ambient audio track combined secondary effects (trees rustling, birds chirping, wind blowing). This method preserved an immersive soundscape while ensuring the prototype remained lightweight and responsive. Future iterations could refine the audio layering to further enhance spatial realism.

### Implementing LOD for performance optimization
To enhance performance without sacrificing visual quality, Level of Detail (LOD) optimization was applied to complex 3D models. This technique dynamically adjusts model complexity based on the user's distance, ensuring high detail up close while reducing polygon count for distant objects. During testing, the scene initially struggled with excessive GPU load, causing lag, delayed avatar responses, and UI inefficiencies. Despite optimizing textures to meet Scene Vitals constraints, vertex counts remained too high, making LOD implementation essential.

By introducing multiple LOD levels, the experience maintained visual fidelity while significantly improving loading times and frame rates, particularly in open environments with many objects. The system automatically transitions between different LODs as users move, reducing rendering stress. However, noticeable shifts between detail levels occasionally occur, slightly impacting immersion. Future refinements could smooth these transitions, ensuring seamless LOD swaps that enhance both performance and user experience.
