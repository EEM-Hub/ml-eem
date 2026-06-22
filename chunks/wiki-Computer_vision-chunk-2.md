---
source: sources/wiki-Computer_vision.md
source_url: https://en.wikipedia.org/wiki/Computer_vision
chunk: 2/6
---

## Related fields

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/2d/Intersection_over_Union_-_object_detection_bounding_boxes.jpg/250px-Intersection_over_Union_-_object_detection_bounding_boxes.jpg)](./File:Intersection_over_Union_-_object_detection_bounding_boxes.jpg)[Object detection](./Object_detection) in a photograph 

### Solid-state physics

 

[Solid-state physics](./Solid-state_physics) is another field that is closely related to computer vision. Most computer vision systems rely on [image sensors](./Image_sensors), which detect [electromagnetic radiation](./Electromagnetic_radiation), which is typically in the form of either [visible](./Visible_light), [infrared](./Infrared_light) or [ultraviolet light](./Ultraviolet_light). The sensors are designed using [quantum physics](./Quantum_physics). The process by which light interacts with surfaces is explained using physics. Physics explains the behavior of [optics](./Optics) which are a core part of most imaging systems. Sophisticated image sensors even require [quantum mechanics](./Quantum_mechanics) to provide a complete understanding of the image formation process.[[11]](./Computer_vision#cite_note-Szeliski2010-11) Also, various measurement problems in physics can be addressed using computer vision, for example, motion in fluids.

 

### Neurobiology

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/0c/Simplified_neural_network_training_example.svg/250px-Simplified_neural_network_training_example.svg.png)](./File:Simplified_neural_network_training_example.svg)Simplified example of training a neural network in object detection: The network is trained by multiple images that are known to depict [starfish](./Starfish) and [sea urchins](./Sea_urchin), which are correlated with "nodes" that represent visual [features](./Feature_(computer_vision)). The starfish match with a ringed texture and a star outline, whereas most sea urchins match with a striped texture and oval shape. However, the instance of a ring-textured sea urchin creates a weakly weighted association between them.[![](//upload.wikimedia.org/wikipedia/commons/thumb/b/b7/Simplified_neural_network_example.svg/250px-Simplified_neural_network_example.svg.png)](./File:Simplified_neural_network_example.svg)Subsequent run of the network on an input image (left):[[21]](./Computer_vision#cite_note-21) The network correctly detects the starfish. However, the weakly weighted association between ringed texture and sea urchin also confers a weak signal to the latter from one of two intermediate nodes. In addition, a shell that was not included in the training gives a weak signal for the oval shape, also resulting in a weak signal for the sea urchin output. These weak signals may result in a [false positive](./False_positive) result for sea urchin.
In reality, textures and outlines would not be represented by single nodes, but rather by associated weight patterns of multiple nodes. 

[Neurobiology](./Neurobiology) has greatly influenced the development of computer vision algorithms. Over the last century, there has been an extensive study of eyes, neurons, and brain structures devoted to the processing of visual stimuli in both humans and various animals. This has led to a coarse yet convoluted description of how natural vision systems operate in order to solve certain vision-related tasks. These results have led to a sub-field within computer vision where artificial systems are designed to mimic the processing and behavior of biological systems at different levels of complexity. Also, some of the learning-based methods developed within computer vision (*e.g.* [neural net](./Artificial_neural_network) and [deep learning](./Deep_learning) based image and feature analysis and classification) have their background in neurobiology.  The [Neocognitron](./Neocognitron), a neural network developed in the 1970s by [Kunihiko Fukushima](./Kunihiko_Fukushima), is an early example of computer vision taking direct inspiration from neurobiology, specifically the [primary visual cortex](./Visual_cortex#Primary_visual_cortex_(V1)).

 

Some strands of computer vision research are closely related to the study of [biological vision](./Biological_vision)—indeed, just as many strands of [AI](./Artificial_intelligence) research are closely tied with research into human intelligence and the use of stored knowledge to interpret, integrate, and utilize visual information. The field of biological vision studies and models the physiological processes behind visual perception in humans and other animals. Computer vision, on the other hand, develops and describes the algorithms implemented in software and hardware behind artificial vision systems. An interdisciplinary exchange between biological and computer vision has proven fruitful for both fields.[[22]](./Computer_vision#cite_note-TextbookP1-22)

 

### Signal processing

 

Yet another field related to computer vision is [signal processing](./Signal_processing). Many methods for processing one-variable signals, typically temporal signals, can be extended in a natural way to the processing of two-variable signals or multi-variable signals in computer vision. However, because of the specific nature of images, there are many methods developed within computer vision that have no counterpart in the processing of one-variable signals. Together with the multi-dimensionality of the signal, this defines a subfield in signal processing as a part of computer vision.

 

### Robotic navigation

 

[Robot navigation](./Robot_navigation) sometimes deals with autonomous [path planning](./Path_planning) or deliberation for robotic systems to [navigate through an environment](./Robotic_navigation).[[23]](./Computer_vision#cite_note-23) A detailed understanding of these environments is required to navigate through them. Information about the environment could be provided by a computer vision system, acting as a vision sensor and providing high-level information about the environment and the robot

 

### Visual computing

 This section is an excerpt from [Visual computing](./Visual_computing).[[edit](https://en.wikipedia.org/w/index.php?title=Visual_computing&action=edit)] 

[Visual computing](./Visual_computing) is a generic term for all computer science disciplines dealing with images and [3D models](./3D_model), such as [computer graphics](./Computer_graphics), [image processing](./Image_processing), [visualization](./Visualization_(graphics)), computer vision, [virtual](./Virtual_reality) and [augmented reality](./Augmented_reality), [video processing](./Video_processing), and [computational visualistics](./Computational_visualistics). Visual computing also includes aspects of [pattern recognition](./Pattern_recognition), human computer interaction, machine learning and digital libraries. The core challenges are the acquisition, processing, analysis and rendering of visual information (mainly images and video). Application areas include industrial quality control, [medical image processing](./Medical_image_processing) and visualization, surveying, [robotics](./Robotics), multimedia systems, virtual heritage, special effects in movies and television, and [ludology](./Ludology). Visual computing also includes [digital art](./Digital_art) and [digital media](./Digital_media) studies.

   

### Other fields

 

Besides the above-mentioned views on computer vision, many of the related research topics can also be studied from a purely mathematical point of view. For example, many methods in computer vision are based on [statistics](./Statistics), [optimization](./Optimization_(mathematics)) or [geometry](./Geometry). Finally, a significant part of the field is devoted to the implementation aspect of computer vision; how existing methods can be realized in various combinations of software and hardware, or how these methods can be modified in order to gain processing speed without losing too much performance. Computer vision is also used in fashion eCommerce, inventory management, patent search, furniture, and the beauty industry.[[24]](./Computer_vision#cite_note-24)

 

### Distinctions

 

The fields most closely related to computer vision are [image processing](./Image_processing), [image analysis](./Image_analysis) and [machine vision](./Machine_vision). There is a significant overlap in the range of techniques and applications that these cover. This implies that the basic techniques that are used and developed in these fields are similar, something which can be interpreted as there is only one field with different names. On the other hand, it appears to be necessary for research groups, scientific journals, conferences, and companies to present or market themselves as belonging specifically to one of these fields and, hence, various characterizations which distinguish each of the fields from the others have been presented. In image processing, the input and output are both images, whereas in computer vision, the input is an image or video, and the output could be an enhanced image, an analysis of the image's content, or even a system's behavior based on that analysis.

 

[Computer graphics](./Computer_graphics) produces image data from 3D models, and computer vision often produces 3D models from image data.[[25]](./Computer_vision#cite_note-3DVAE-25) There is also a trend towards a combination of the two disciplines, *e.g.*, as explored in [augmented reality](./Augmented_reality).

 

The following characterizations appear relevant but should not be taken as universally accepted:

 
- [Image processing](./Image_processing) and [image analysis](./Image_analysis) tend to focus on 2D images, how to transform one image to another, *e.g.*, by pixel-wise operations such as contrast enhancement, local operations such as edge extraction or noise removal, or geometrical transformations such as rotating the image. This characterization implies that image processing/analysis neither requires assumptions nor produces interpretations about the image content.
- Computer vision includes 3D analysis from 2D images. This analyzes the 3D scene projected onto one or several images, *e.g.*, how to reconstruct structure or other information about the 3D scene from one or several images. Computer vision often relies on more or less complex assumptions about the scene depicted in an image.
- [Machine vision](./Machine_vision) is the process of applying a range of technologies and methods to provide imaging-based automatic inspection, process control, and robot guidance[[26]](./Computer_vision#cite_note-NASAarticle-26) in industrial applications.[[22]](./Computer_vision#cite_note-TextbookP1-22) Machine vision tends to focus on applications, mainly in manufacturing, *e.g.*, vision-based robots and systems for vision-based inspection, measurement, or picking (such as [bin picking](./Bin_picking)[[27]](./Computer_vision#cite_note-27)). This implies that image sensor technologies and control theory often are integrated with the processing of image data to control a robot and that real-time processing is emphasized by means of efficient implementations in hardware and software. It also implies that external conditions such as lighting can be and are often more controlled in machine vision than they are in general computer vision, which can enable the use of different algorithms.
- There is also a field called [imaging](./Imaging_science) which primarily focuses on the process of producing images, but sometimes also deals with the processing and analysis of images. For example, [medical imaging](./Medical_imaging) includes substantial work on the analysis of image data in medical applications. Progress in [convolutional neural networks](./Convolutional_neural_network) (CNNs) has improved the accurate detection of disease in medical images, particularly in cardiology, pathology, dermatology, and radiology.[[28]](./Computer_vision#cite_note-28)
- Finally, [pattern recognition](./Pattern_recognition) is a field that uses various methods to extract information from signals in general, mainly based on statistical approaches and [artificial neural networks](./Artificial_neural_networks).[[29]](./Computer_vision#cite_note-29) A significant part of this field is devoted to applying these methods to image data.

 

[Photogrammetry](./Photogrammetry) also overlaps with computer vision, e.g., [stereophotogrammetry](./Stereophotogrammetry) vs. [computer stereo vision](./Computer_stereo_vision).

 


