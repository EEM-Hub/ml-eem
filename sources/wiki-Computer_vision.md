---
source: https://en.wikipedia.org/wiki/Computer_vision
fetched: 2026-06-21
---

Computerized information extraction from images 
| Part ofa serieson |
| --- |
| Artificial intelligence (AI) |
| Major goalsArtificial general intelligenceIntelligent agentRecursive self-improvementPlanningComputer visionGeneral game playingKnowledge representationNatural language processingRoboticsAI safety |
| ApproachesMachine learningSymbolicDeep learningBayesian networksEvolutionary algorithmsNeuro-symbolic AISystems integrationOpen-sourceAI data centers |
| ApplicationsBioinformaticsDeepfakeEarth sciencesFinanceGenerative AIArtAudioMusicGovernmentHealthcareIndustrySoftware developmentTranslationMilitaryPhysicsProjects |
| PhilosophyAI alignmentArtificial consciousnessThe bitter lessonChinese roomFriendly AIEthicsExistential riskTuring testUncanny valleyHuman–AI interaction |
| HistoryTimelineProgressAI winterAI boomAI bubble |
| ControversiesDeepfake pornographyTaylor Swift deepfake pornography controversyGrok sexual deepfake scandalGoogle Gemini image generation controversyIt's the Most Terrible Time of the YearPause Giant AI ExperimentsRemoval of Sam Altman from OpenAIStatement on AI RiskTay (chatbot)Théâtre D'opéra SpatialVoiceverse NFT plagiarism scandal |
| GlossaryGlossary |
| vte |

 

**Computer vision** tasks include methods for [acquiring](./Image_sensor), [processing](./Image_processing), [analyzing](./Image_analysis), and understanding [digital images](./Digital_image), and extraction of [high-dimensional](./High-dimensional) data from the real world in order to produce numerical or symbolic information, e.g. in the form of decisions.[[1]](./Computer_vision#cite_note-Klette-2014-1)[[2]](./Computer_vision#cite_note-Shapiro-Stockman-2001-2)[[3]](./Computer_vision#cite_note-Morris-2004-3)[[4]](./Computer_vision#cite_note-Jahne-Haussecker-2000-4) "Understanding" in this context signifies the transformation of visual images into descriptions of the world that make sense to thought processes and can elicit appropriate action. This image understanding can be seen as the disentangling of symbolic information from image data using models constructed with the aid of [geometry](./Geometry), [physics](./Physics), [statistics](./Statistics), and learning theory.

 

The [scientific discipline](./Scientific_discipline) of computer vision is concerned with the theory behind artificial systems that extract information from images. Image data can take many forms, such as video sequences, views from multiple cameras, multi-dimensional data from a [3D scanner](./3D_scanning), 3D point clouds from [LiDaR](./Lidar) sensors, or medical scanning devices. The technological discipline of computer vision seeks to apply its theories and models to the construction of computer vision systems.

 

Subdisciplines of computer vision include [scene reconstruction](./3D_reconstruction), [object detection](./Object_detection), [event detection](./Event_detection), [activity recognition](./Activity_recognition), [video tracking](./Video_tracking), [object recognition](./Object_recognition), [3D pose estimation](./3D_pose_estimation), learning, indexing, [motion estimation](./Motion_estimation), [visual servoing](./Visual_servoing), [3D scene modeling](./3D_modeling), and [image restoration](./Digital_photograph_restoration).

 

## Definition

 

Computer vision is an [interdisciplinary field](./Interdisciplinarity) that deals with how computers can be made to gain high-level understanding from [digital images](./Digital_image) or [videos](./Video). From the perspective of [engineering](./Engineering), it seeks to automate tasks that the [human visual system](./Human_visual_system) can do.[[5]](./Computer_vision#cite_note-Ballard-Brown-1982-5)[[6]](./Computer_vision#cite_note-Huang-1996-6)[[7]](./Computer_vision#cite_note-Sonka-Hlavac-Boyle-2008-7) "Computer vision is concerned with the automatic extraction, analysis, and understanding of useful information from a single image or a sequence of images. It involves the development of a theoretical and algorithmic basis to achieve automatic visual understanding."[[8]](./Computer_vision#cite_note-bmva-8) As a [scientific discipline](./Scientific_discipline), computer vision is concerned with the theory behind artificial systems that extract information from images. The image data can take many forms, such as video sequences, views from multiple cameras, or multi-dimensional data from a [medical scanner](./Medical_scanner).[[9]](./Computer_vision#cite_note-9) As a technological discipline, computer vision seeks to apply its theories and models for the construction of computer vision systems. [Machine vision](./Machine_vision) refers to a systems engineering discipline, especially in the context of factory automation. In more recent times, the terms computer vision and machine vision have converged to a greater degree.[[10]](./Computer_vision#cite_note-davies5-10): 13 

 

## History

 

In the late 1960s, computer vision began at universities that were pioneering [artificial intelligence](./Artificial_intelligence). It was meant to mimic the [human visual system](./Human_visual_system) as a stepping stone to endowing robots with intelligent behavior.[[11]](./Computer_vision#cite_note-Szeliski2010-11) In 1966, it was believed that this could be achieved through an undergraduate summer project,[[12]](./Computer_vision#cite_note-12) by attaching a camera to a computer and having it "describe what it saw".[[13]](./Computer_vision#cite_note-Seymour1966-13)[[14]](./Computer_vision#cite_note-Boden2006-14)

 

What distinguished computer vision from the prevalent field of [digital image processing](./Digital_image_processing) at that time was a desire to extract [three-dimensional](./Three-dimensional) structure from images with the goal of achieving full scene understanding. Studies in the 1970s formed the early foundations for many of the computer vision [algorithms](./Algorithm) that exist today, including [extraction of edges](./Edge_detection) from images, labeling of lines, non-polyhedral and [polyhedral modeling](./Polyhedron_model), representation of objects as interconnections of smaller structures, [optical flow](./Optical_flow), and [motion estimation](./Motion_estimation).[[11]](./Computer_vision#cite_note-Szeliski2010-11)

 

The next decade saw studies based on more rigorous mathematical analysis and quantitative aspects of computer vision. These include the concept of [scale-space](./Scale_space), the inference of shape from various cues such as [shading](./Shading), texture and focus, and [contour models known as snakes](./Active_contour_model). Researchers also realized that many of these mathematical concepts could be treated within the same optimization framework as [regularization](./Regularization_(mathematics)) and [Markov random fields](./Markov_random_field).[[15]](./Computer_vision#cite_note-Kanade20122-15)
By the 1990s, some of the previous research topics became more active than others. Research in [projective](./Projective_geometry) [3-D reconstructions](./3D_reconstruction) led to better understanding of [camera calibration](./Camera_resectioning). With the advent of optimization methods for camera calibration, it was realized that a lot of the ideas were already explored in [bundle adjustment](./Bundle_adjustment) theory from the field of [photogrammetry](./Photogrammetry). This led to methods for sparse [3-D reconstructions of scenes from multiple images](./3D_reconstruction_from_multiple_images). Progress was made on the dense stereo [correspondence problem](./Correspondence_problem) and further multi-view stereo techniques. At the same time, [variations of graph cut](./Graph_cuts_in_computer_vision) were used to solve [image segmentation](./Image_segmentation). This decade also marked the first time statistical learning techniques were used in practice to recognize faces in images (see [Eigenface](./Eigenface)). Toward the end of the 1990s, a significant change came about with the increased interaction between the fields of [computer graphics](./Computer_graphics_(computer_science)) and computer vision. This included [image-based rendering](./Image-based_rendering), [image morphing](./Morphing), view interpolation, [panoramic image stitching](./Image_stitching) and early [light-field rendering](./Light_field).[[11]](./Computer_vision#cite_note-Szeliski2010-11)

 

Recent work has seen the resurgence of [feature](./Feature_(computer_vision))-based methods used in conjunction with machine learning techniques and complex optimization frameworks.[[16]](./Computer_vision#cite_note-Sebe2005-16)[[17]](./Computer_vision#cite_note-Freeman2008-17) 
The advancement of [Deep Learning](./Deep_learning) techniques has brought further life to the field of computer vision. The accuracy of deep learning algorithms on several benchmark computer vision data sets for tasks ranging from classification,[[18]](./Computer_vision#cite_note-NatureBengio-18) segmentation and optical flow has surpassed prior methods.[[19]](./Computer_vision#cite_note-19)[[20]](./Computer_vision#cite_note-20)

 

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

 

## Applications

 

Applications range from tasks such as industrial [machine vision](./Machine_vision) systems which, say, inspect bottles speeding by on a production line, to research into artificial intelligence and computers or robots that can comprehend the world around them. The computer vision and machine vision fields have significant overlap. Computer vision covers the core technology of automated image analysis which is used in many fields. Machine vision usually refers to a process of combining automated image analysis with other methods and technologies to provide automated inspection and robot guidance in industrial applications. In many computer-vision applications, computers are pre-programmed to solve a particular task, but methods based on learning are now becoming increasingly common. Examples of applications of computer vision include systems for:

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Synthesizing_3D_Shapes_via_Modeling_Multi-View_Depth_Maps_and_Silhouettes_With_Deep_Generative_Networks.png/250px-Synthesizing_3D_Shapes_via_Modeling_Multi-View_Depth_Maps_and_Silhouettes_With_Deep_Generative_Networks.png)](./File:Synthesizing_3D_Shapes_via_Modeling_Multi-View_Depth_Maps_and_Silhouettes_With_Deep_Generative_Networks.png)Learning 3D shapes has been a challenging task in computer vision. Recent advances in [deep learning](./Deep_learning) have enabled researchers to build models that are able to generate and reconstruct 3D shapes from single or multi-view [depth maps](./Depth_map) or silhouettes seamlessly and efficiently.[[25]](./Computer_vision#cite_note-3DVAE-25) 
- Automatic inspection, *e.g.*, in manufacturing applications;
- Assisting humans in identification tasks, e.g., a [species identification](./Automated_species_identification) system;[[30]](./Computer_vision#cite_note-30)
- Controlling processes, *e.g.*, an [industrial robot](./Industrial_robots);
- [Detecting events](./Activity_recognition), *e.g.*, for [visual surveillance](./Artificial_intelligence_for_video_surveillance) or [people counting](./People_counter), e.g., in the [restaurant industry](./Presto_(restaurant_technology_platform));
- Interaction, *e.g.*, as the input to a device for [computer-human interaction](./Computer-human_interaction);
- [MediaPipe](./MediaPipe), an open-source framework from Google for AI edge device computing, *e.g.*, face detection, image classification, object detection;
- monitoring agricultural crops, e.g. an open-source [vision transformers](./Vision_transformer) model[[31]](./Computer_vision#cite_note-31)  has been developed to help farmers automatically detect [strawberry diseases](./List_of_strawberry_diseases) with 98.4% accuracy.[[32]](./Computer_vision#cite_note-32)
- Modeling objects or environments, *e.g.*, medical image analysis or [topographical](./Topographic_map) modeling;
- Navigation, *e.g.*, by an [autonomous vehicle](./Autonomous_vehicle) or [mobile robot](./Mobile_robot);
- Organizing information, *e.g.*, for [indexing](./Search_engine_indexing) databases of images and image sequences.
- Tracking surfaces or planes in 3D coordinates for allowing [Augmented Reality](./Augmented_reality) experiences.
- Analyzing the condition of facilities in industry or construction.
- Automatic real-time lip-reading for devices and apps to assist people with disabilities.[[33]](./Computer_vision#cite_note-33)

 

For 2024, the leading areas of computer vision were industry (market size US$5.22 billion),[[34]](./Computer_vision#cite_note-34) medicine (market size US$2.6 billion),[[35]](./Computer_vision#cite_note-35) military (market size US$996.2 million).[[36]](./Computer_vision#cite_note-36)

 

### Medicine

 [DARPA](./DARPA)'s Visual Media Reasoning concept video 

One of the most prominent application fields is [medical computer vision](./Medical_computer_vision), or medical image processing, characterized by the extraction of information from image data to [diagnose a patient.](./Computer-assisted_diagnosis)[[37]](./Computer_vision#cite_note-37) An example of this is the detection of [tumours](./Tumour), [arteriosclerosis](./Arteriosclerosis) or other malign changes, and a variety of dental pathologies; measurements of organ dimensions, blood flow, etc. are another example. It also supports medical research by providing new information: *e.g.*, about the structure of the brain or the quality of medical treatments. Applications of computer vision in the medical area also include enhancement of images interpreted by humans—[ultrasonic images](./Ultrasound) or [X-ray images](./Radiography), for example—to reduce the influence of noise.

 

### Machine vision

 

A second application area in computer vision is in industry, sometimes called [machine vision](./Machine_vision), where information is extracted for the purpose of supporting a production process. One example is quality control where details or final products are being automatically inspected in order to find defects. One of the most prevalent fields for such inspecti is the [Wafer](./Wafer_(electronics)) industry in which every single Wafer is being measured and inspected for inaccuracies or defects to prevent a [computer chip](./Integrated_circuit) from coming to market in an unusable manner. Another example is a measurement of the position and orientation of details to be picked up by a robot arm. Machine vision is also heavily used in the agricultural processes to remove undesirable foodstuff from bulk material, a process called [optical sorting](./Optical_sorting).[[38]](./Computer_vision#cite_note-Davies-2005-38)

 

### Military

 

The obvious examples are the detection of enemy soldiers or vehicles and [missile guidance](./Missile_guidance). More advanced systems for missile guidance send the missile to an area rather than a specific target, and target selection is made when the missile reaches the area based on locally acquired image data. Modern military concepts, such as "battlefield awareness", imply that various sensors, including image sensors, provide a rich set of information about a combat scene that can be used to support strategic decisions. In this case, automatic processing of the data is used to reduce complexity and to fuse information from multiple sensors to increase reliability.

 

### Autonomous vehicles

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/9/96/Mars_Science_Laboratory%2C_2011-Present.jpg/250px-Mars_Science_Laboratory%2C_2011-Present.jpg)](./File:Mars_Science_Laboratory,_2011-Present.jpg)Artist's concept of *[Curiosity](./Curiosity_(rover))*, an example of an uncrewed land-based vehicle. The [stereo camera](./Stereo_camera) is mounted on top of the rover. 

One of the newer application areas is autonomous vehicles, which include [submersibles](./Submersible), land-based vehicles (small robots with wheels, cars, or trucks), aerial vehicles, and unmanned aerial vehicles ([UAV](./Unmanned_aerial_vehicle)). The level of autonomy ranges from fully autonomous (unmanned) vehicles to vehicles where computer-vision-based systems support a driver or a pilot in various situations. Fully autonomous vehicles typically use computer vision for navigation, e.g., for knowing where they are or mapping their environment ([SLAM](./Simultaneous_localization_and_mapping)), for detecting obstacles. It can also be used for detecting certain task-specific events, *e.g.*, a UAV looking for forest fires. Examples of supporting systems are obstacle warning systems in cars, cameras and LiDAR sensors in vehicles, and systems for autonomous landing of aircraft. Several car manufacturers have demonstrated systems for [autonomous driving of cars](./Driverless_car). There are ample examples of military autonomous vehicles ranging from advanced missiles to UAVs for recon missions or missile guidance. Space exploration is already being made with autonomous vehicles using computer vision, *e.g.*, [NASA](./NASA)'s *[Curiosity](./Curiosity_(rover))* and [CNSA](./China_National_Space_Administration)'s *[Yutu-2](./Yutu-2)* rover.

 

### Tactile feedback

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/3/3d/Finger_sensor.webp/330px-Finger_sensor.webp.png)](./File:Finger_sensor.webp)Rubber artificial skin layer with the flexible structure for the shape estimation of micro-undulation surfaces [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/cc/Silicon_Sensor.webp/330px-Silicon_Sensor.webp.png)](./File:Silicon_Sensor.webp)Above is a silicon mold with a camera inside containing many different point markers. When this sensor is pressed against the surface, the silicon deforms, and the position of the point markers shifts. A computer can then take this data and determine how exactly the mold is pressed against the surface. This can be used to calibrate robotic hands in order to make sure they can grasp objects effectively. 

Materials such as rubber and silicon are being used to create sensors that allow for applications such as detecting microundulations and calibrating robotic hands. Rubber can be used in order to create a mold that can be placed over a finger, inside of this mold would be multiple strain gauges. The finger mold and sensors could then be placed on top of a small sheet of rubber containing an array of rubber pins. A user can then wear the finger mold and trace a surface. A computer can then read the data from the strain gauges and measure if one or more of the pins are being pushed upward. If a pin is being pushed upward then the computer can recognize this as an imperfection in the surface. This sort of technology is useful in order to receive accurate data on imperfections on a very large surface.[[39]](./Computer_vision#cite_note-:0-39) Another variation of this finger mold sensor are sensors that contain a camera suspended in silicon. The silicon forms a dome around the outside of the camera and embedded in the silicon are point markers that are equally spaced. These cameras can then be placed on devices such as robotic hands in order to allow the computer to receive highly accurate tactile data.[[40]](./Computer_vision#cite_note-:1-40)

 

### Other applications

 

Other application areas include:

 
- Support of [visual effects](./Visual_effects) creation for cinema and broadcast, *e.g.*, [camera tracking](./Camera_tracking) (match moving).
- [Surveillance](./Surveillance).
- [Driver drowsiness detection](./Driver_drowsiness_detection)[[41]](./Computer_vision#cite_note-41)[[42]](./Computer_vision#cite_note-42)[[43]](./Computer_vision#cite_note-43)
- Tracking and counting organisms in the biological sciences[[44]](./Computer_vision#cite_note-BruijningVisser2018-44) (for example in leaf counting for food crops).[[45]](./Computer_vision#cite_note-45)

 

## Typical tasks

 

Each of the application areas described above employ a range of computer vision tasks; more or less well-defined measurement problems or processing problems, which can be solved using a variety of methods. Some examples of typical computer vision tasks are presented below.

 

Computer vision tasks include methods for [acquiring](./Image_sensor), [processing](./Image_processing), [analyzing](./Image_analysis) and understanding digital images, and extraction of [high-dimensional](./High-dimensional) data from the real world in order to produce numerical or symbolic information, *e.g.*, in the forms of decisions.[[1]](./Computer_vision#cite_note-Klette-2014-1)[[2]](./Computer_vision#cite_note-Shapiro-Stockman-2001-2)[[3]](./Computer_vision#cite_note-Morris-2004-3)[[4]](./Computer_vision#cite_note-Jahne-Haussecker-2000-4) Understanding in this context means the transformation of visual images into descriptions of the world that can interface with other thought processes and elicit appropriate action. This image understanding can be seen as the disentangling of symbolic information from image data using models constructed with the aid of geometry, physics, statistics, and learning theory.[[46]](./Computer_vision#cite_note-Forsyth-Ponce-2003-46)

 

### Recognition

 

The classical problem in computer vision, image processing, and [machine vision](./Machine_vision) is that of determining whether or not the image data contains some specific object, feature, or activity. Different varieties of recognition problem are described in the literature.[[47]](./Computer_vision#cite_note-Forsyth2012-47)

 
- **[Object recognition](./Object_recognition)** (also called **object classification**) – one or several pre-specified or learned objects or object classes can be recognized, usually together with their 2D positions in the image or 3D poses in the scene. Blippar, [Google Goggles](./Google_Goggles), and LikeThat provide stand-alone programs that illustrate this functionality.
- **Identification** – an individual instance of an object is recognized. Examples include identification of a specific person's face or fingerprint, [identification of handwritten digits](./Handwriting_recognition), or the identification of a specific vehicle.
- **[Detection](./Object_detection)** – the image data are scanned for specific objects along with their locations. Examples include the detection of an obstacle in the car's field of view and possible abnormal cells or tissues in medical images or the detection of a vehicle in an automatic road toll system. Detection based on relatively simple and fast computations is sometimes used for finding smaller regions of interesting image data which can be further analyzed by more computationally demanding techniques to produce a correct interpretation.

 

Currently, the best algorithms for such tasks are based on [convolutional neural networks](./Convolutional_neural_network). An illustration of their capabilities is given by the [ImageNet Large Scale Visual Recognition Challenge](./ImageNet#ImageNet_Challenge); this is a benchmark in object classification and detection, with millions of images and 1000 object classes used in the competition.[[48]](./Computer_vision#cite_note-:2-48) Performance of convolutional neural networks on the ImageNet tests is now close to that of humans.[[48]](./Computer_vision#cite_note-:2-48) The best algorithms still struggle with objects that are small or thin, such as a small ant on the stem of a flower or a person holding a quill in their hand. They also have trouble with images that have been distorted with filters (an increasingly common phenomenon with modern digital cameras). By contrast, those kinds of images rarely trouble humans. Humans, however, tend to have trouble with other issues. For example, they are not good at classifying objects into fine-grained classes, such as the particular breed of dog or species of bird, whereas convolutional neural networks handle this with ease.[*[citation needed](./Wikipedia:Citation_needed)*]

 

Several specialized tasks based on recognition exist, such as:

 
- **[Content-based image retrieval](./Content-based_image_retrieval)** – finding all images in a larger set of images which have a specific content. The content can be specified in different ways, for example in terms of similarity relative to a target image (give me all images similar to image X) by utilizing [reverse image search](./Reverse_image_search) techniques, or in terms of high-level search criteria given as text input (give me all images which contain many houses, are taken during winter and have no cars in them).

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/ed/SRT_Shape_Recognition_Technology.png/250px-SRT_Shape_Recognition_Technology.png)](./File:SRT_Shape_Recognition_Technology.png)Computer vision for [people counter](./People_counter) purposes in public places, malls, shopping centers 
- **[Pose estimation](./Pose_(computer_vision))** – estimating the position or orientation of a specific object relative to the camera. An example application for this technique would be assisting a robot arm in retrieving objects from a conveyor belt in an [assembly line](./Assembly_line) situation or picking parts from a bin.
- **[Optical character recognition](./Optical_character_recognition)** (OCR) – identifying [characters](./Character_(computing)) in images of printed or handwritten text, usually with a view to encoding the text in a format more amenable to editing or [indexing](./Search_index) (*e.g.* [ASCII](./ASCII)). A related task is reading of 2D codes such as [data matrix](./Data_Matrix) and [QR](./QR_code) codes.
- **[Facial recognition](./Facial_recognition_system) – ** a technology that enables the matching of faces in digital images or video frames to a face database, which is now widely used for mobile phone facelock, smart door locking, etc.[[49]](./Computer_vision#cite_note-49)
- [Emotion recognition](./Emotion_recognition)** – **a subset of facial recognition, emotion recognition refers to the process of classifying human [emotions.](./Emotion) Psychologists caution, however, that internal emotions cannot be reliably detected from faces.[[50]](./Computer_vision#cite_note-50)
- **[Shape Recognition Technology](./Pattern_recognition)** (SRT) in [people counter](./People_counter) systems differentiating human beings (head and shoulder patterns) from objects.
- **[Human activity recognition](./Activity_recognition)** - deals with recognizing the activity from a series of video frames, such as, if the person is picking up an object or walking.

 

### Motion analysis

 

Several tasks relate to motion estimation, where an image sequence is processed to produce an estimate of the velocity either at each points in the image or in the 3D scene or even of the camera that produces the images. Examples of such tasks are:

 
- **[Egomotion](./Egomotion)** – determining the 3D rigid motion (rotation and translation) of the camera from an image sequence produced by the camera.
- **[Tracking](./Video_tracking)** – following the movements of a (usually) smaller set of interest points or objects (*e.g.*, vehicles, objects, humans or other organisms[[44]](./Computer_vision#cite_note-BruijningVisser2018-44)) in the image sequence. This has vast industry applications as most high-running machinery can be monitored in this way.
- **[Optical flow](./Optical_flow)** – to determine, for each point in the image, how that point is moving relative to the image plane, *i.e.*, its apparent motion. This motion is a result of both how the corresponding 3D point is moving in the scene and how the camera is moving relative to the scene.

 

### Scene reconstruction

 

Given one or (typically) more images of a scene, or a video, scene reconstruction aims at [computing a 3D model](./3D_reconstruction) of the scene. In the simplest case, the model can be a set of 3D points. More sophisticated methods produce a complete 3D surface model. The advent of 3D imaging not requiring motion or scanning, and related processing algorithms is enabling rapid advances in this field. Grid-based 3D sensing can be used to acquire 3D images from multiple angles. Algorithms are now available to stitch multiple 3D images together into point clouds and 3D models.[[25]](./Computer_vision#cite_note-3DVAE-25)

 

### Image restoration

 

Image restoration comes into the picture when the original image is degraded or damaged due to some external factors like lens wrong positioning, transmission interference, low lighting or motion blurs, etc., which is referred to as noise. When the images are degraded or damaged, the information to be extracted from them also gets damaged. Therefore, we need to recover or restore the image as it was intended to be. The aim of image restoration is the removal of noise (sensor noise, motion blur, etc.) from images. The simplest possible approach for noise removal is various types of filters, such as low-pass filters or median filters. More sophisticated methods assume a model of how the local image structures look to distinguish them from noise. By first analyzing the image data in terms of the local image structures, such as lines or edges, and then controlling the filtering based on local information from the analysis step, a better level of noise removal is usually obtained compared to the simpler approaches.

 

An example in this field is [inpainting](./Inpainting).

 

## System methods

 

The organization of a computer vision system is highly application-dependent. Some systems are stand-alone applications that solve a specific measurement or detection problem, while others constitute a sub-system of a larger design which, for example, also contains sub-systems for control of mechanical actuators, planning, information databases, man-machine interfaces, etc. The specific implementation of a computer vision system also depends on whether its functionality is pre-specified or if some part of it can be learned or modified during operation. Many functions are unique to the application. There are, however, typical functions that are found in many computer vision systems.

 
- **Image acquisition** – A digital image is produced by one or several [image sensors](./Image_sensor), which, besides various types of light-sensitive cameras, include [range sensors](./Rangefinder_camera), tomography devices, radar, ultra-sonic cameras, etc. Depending on the type of sensor, the resulting image data is an ordinary 2D image, a 3D volume, or an image sequence. The pixel values typically correspond to light intensity in one or several spectral bands (gray images or colour images) but can also be related to various physical measures, such as depth, absorption or reflectance of sonic or electromagnetic waves, or [magnetic resonance imaging](./Magnetic_resonance_imaging).[[38]](./Computer_vision#cite_note-Davies-2005-38)
- **Pre-processing** – Before a computer vision method can be applied to image data in order to extract some specific piece of information, it is usually necessary to process the data in order to ensure that it satisfies certain assumptions implied by the method. Examples are:

- Re-sampling to ensure that the image coordinate system is correct.
- Noise reduction to ensure that sensor noise does not introduce false information.
- Contrast enhancement to ensure that relevant information can be detected.
- [Scale space](./Scale_space) representation to enhance image structures at locally appropriate scales.

- **[Feature extraction](./Feature_detection_(computer_vision))** – Image features at various levels of complexity are extracted from the image data.[[38]](./Computer_vision#cite_note-Davies-2005-38) Typical examples of such features are:

- Lines, [edges](./Edge_detection) and [ridges](./Ridge_detection).
- Localized [interest points](./Interest_point_detection) such as [corners](./Corner_detection), [blobs](./Blob_detection) or points.

 More complex features may be related to texture, shape, or motion. 
- **[Detection](./Object_detection)/[segmentation](./Image_segmentation)** – At some point in the processing, a decision is made about which image points or regions of the image are relevant for further processing.[[38]](./Computer_vision#cite_note-Davies-2005-38) Examples are:

- Selection of a specific set of interest points.
- Segmentation of one or multiple image regions that contain a specific object of interest.
- Segmentation of image into nested scene architecture comprising foreground, object groups, single objects or [salient](./Salience_(neuroscience)) object[[51]](./Computer_vision#cite_note-51) parts (also referred to as spatial-taxon scene hierarchy),[[52]](./Computer_vision#cite_note-52) while the [visual salience](./Salience_(neuroscience)) is often implemented as [spatial](./Visual_spatial_attention) and [temporal attention](./Visual_temporal_attention).
- Segmentation or [co-segmentation](./Object_co-segmentation) of one or multiple videos into a series of per-frame foreground masks while maintaining its temporal semantic continuity.[[53]](./Computer_vision#cite_note-Liu_Wang_Hua_Zhang_2018_pp._5840–5853-53)[[54]](./Computer_vision#cite_note-Wang_Duan_Zhang_Niu_p=1657-54)

- **High-level processing** – At this step, the input is typically a small set of data, for example, a set of points or an image region, which is assumed to contain a specific object.[[38]](./Computer_vision#cite_note-Davies-2005-38) The remaining processing deals with, for example:

- Verification that the data satisfies model-based and application-specific assumptions.
- Estimation of application-specific parameters, such as object pose or object size.
- [Image recognition](./Image_recognition) – classifying a detected object into different categories.
- [Image registration](./Image_registration) – comparing and combining two different views of the same object.

- **Decision making** Making the final decision required for the application,[[38]](./Computer_vision#cite_note-Davies-2005-38) for example:

- Pass/fail on automatic inspection applications.
- Match/no-match in recognition applications.
- Flag for further human review in medical, military, security and recognition applications.

 

### Image-understanding systems

 

Image-understanding systems (IUS) include three levels of abstraction as follows: low level includes image primitives such as edges, texture elements, or regions; intermediate level includes boundaries, surfaces and volumes; and high level includes objects, scenes, or events. Many of these requirements are entirely topics for further research.

 

The representational requirements in the designing of IUS for these levels are: representation of prototypical concepts, concept organization, spatial knowledge, temporal knowledge, scaling, and description by comparison and differentiation.

 

While inference refers to the process of deriving new, not explicitly represented facts from currently known facts, control refers to the process that selects which of the many inference, search, and matching techniques should be applied at a particular stage of processing. Inference and control requirements for IUS are: search and hypothesis activation, matching and hypothesis testing, generation and use of expectations, change and focus of attention, certainty and strength of belief, inference and goal satisfaction.[[55]](./Computer_vision#cite_note-55)

 

## Hardware

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/d/d4/LiDAR_Scanner_and_Back_Camera_of_iPad_Pro_2020_-_3.jpg/250px-LiDAR_Scanner_and_Back_Camera_of_iPad_Pro_2020_-_3.jpg)](./File:LiDAR_Scanner_and_Back_Camera_of_iPad_Pro_2020_-_3.jpg)A [2020 model iPad Pro](./IPad_Pro_(4th_generation)) with a [LiDAR](./LiDAR) sensor 

There are many kinds of computer vision systems; however, all of them contain these basic elements: a power source, at least one image acquisition device (camera, ccd, etc.), a processor, and control and communication cables or some kind of wireless interconnection mechanism. In addition, a practical vision system contains software, as well as a display in order to monitor the system. Vision systems for inner spaces, as most industrial ones, contain an illumination system and may be placed in a controlled environment. Furthermore, a completed system includes many accessories, such as camera supports, cables, and connectors.

 

Most computer vision systems use visible-light cameras passively viewing a scene at frame rates of at most 60 frames per second (usually far slower).

 

A few computer vision systems use image-acquisition hardware with active illumination or something other than visible light or both, such as [structured-light 3D scanners](./Structured-light_3D_scanner), [thermographic cameras](./Thermographic_camera), [hyperspectral imagers](./Hyperspectral_imager), [radar imaging](./Radar_imaging), [lidar](./Lidar) scanners, [magnetic resonance images](./Magnetic_resonance_image), [side-scan sonar](./Side-scan_sonar), [synthetic aperture sonar](./Synthetic_aperture_sonar), etc. Such hardware captures "images" that are then processed often using the same computer vision algorithms used to process visible-light images.

 

While traditional broadcast and consumer video systems operate at a rate of 30 frames per second, advances in [digital signal processing](./Digital_signal_processing) and [consumer graphics hardware](./Graphics_processing_unit) has made high-speed image acquisition, processing, and display possible for real-time systems on the order of hundreds to thousands of frames per second. For applications in robotics, fast, real-time video systems are critically important and often can simplify the processing needed for certain algorithms. When combined with a high-speed projector, fast image acquisition allows 3D measurement and feature tracking to be realized.[[56]](./Computer_vision#cite_note-56)

 

[Egocentric vision](./Egocentric_vision) systems are composed of a wearable camera that automatically take pictures from a first-person perspective.

 

As of 2016, [vision processing units](./Vision_processing_unit) are emerging as a new class of processors to complement CPUs and [graphics processing units](./Graphics_processing_units) (GPUs) in this role.[[57]](./Computer_vision#cite_note-the_rise_of_VPUs-57)

 

## See also

  
- [Chessboard detection](./Chessboard_detection)
- [Computational imaging](./Computational_imaging)
- [Computational photography](./Computational_photography)
- [Computer audition](./Computer_audition)
- [Egocentric vision](./Egocentric_vision)
- [Machine vision glossary](./Machine_vision_glossary)
- [Space mapping](./Space_mapping)
- [Teknomo–Fernandez algorithm](./Teknomo–Fernandez_algorithm)
- [Vision science](./Vision_science)
- [Visual agnosia](./Visual_agnosia)
- [Visual perception](./Visual_perception)
- [Visual system](./Visual_system)

  

### Lists

 
- [Outline of computer vision](./Outline_of_computer_vision)
- [List of emerging technologies](./List_of_emerging_technologies)
- [List of robotics software](./List_of_robotics_software)
- [Outline of artificial intelligence](./Outline_of_artificial_intelligence)

 

## References

 
1. [1](./Computer_vision#cite_ref-Klette-2014_1-0) [2](./Computer_vision#cite_ref-Klette-2014_1-1)  Reinhard Klette (2014). *Concise Computer Vision*. Springer. [ISBN](./ISBN_(identifier)) [978-1-4471-6320-6](./Special:BookSources/978-1-4471-6320-6).
2. [1](./Computer_vision#cite_ref-Shapiro-Stockman-2001_2-0) [2](./Computer_vision#cite_ref-Shapiro-Stockman-2001_2-1)  [Linda G. Shapiro](./Linda_Shapiro); George C. Stockman (2001). *Computer Vision*. Prentice Hall. [ISBN](./ISBN_(identifier)) [978-0-13-030796-5](./Special:BookSources/978-0-13-030796-5).
3. [1](./Computer_vision#cite_ref-Morris-2004_3-0) [2](./Computer_vision#cite_ref-Morris-2004_3-1) Tim Morris (2004). *Computer Vision and Image Processing*. Palgrave Macmillan. [ISBN](./ISBN_(identifier)) [978-0-333-99451-1](./Special:BookSources/978-0-333-99451-1).
4. [1](./Computer_vision#cite_ref-Jahne-Haussecker-2000_4-0) [2](./Computer_vision#cite_ref-Jahne-Haussecker-2000_4-1) Bernd Jähne; Horst Haußecker (2000). *Computer Vision and Applications, A Guide for Students and Practitioners*. Academic Press. [ISBN](./ISBN_(identifier)) [978-0-13-085198-7](./Special:BookSources/978-0-13-085198-7).
5. [↑](./Computer_vision#cite_ref-Ballard-Brown-1982_5-0) Dana H. Ballard; Christopher M. Brown (1982). [*Computer Vision*](https://archive.org/details/computervision0000ball). Prentice Hall. [ISBN](./ISBN_(identifier)) [978-0-13-165316-0](./Special:BookSources/978-0-13-165316-0).
6. [↑](./Computer_vision#cite_ref-Huang-1996_6-0) Huang, T. (1996-11-19). Vandoni, Carlo E (ed.). [*Computer Vision: Evolution And Promise*](https://cds.cern.ch/record/400313/files/p21.pdf) (PDF). [19th CERN School of Computing](https://cds.cern.ch/record/300250). Geneva: CERN. pp. 21–25. [doi](./Doi_(identifier)):[10.5170/CERN-1996-008.21](https://doi.org/10.5170%2FCERN-1996-008.21). [ISBN](./ISBN_(identifier)) [978-92-9083-095-5](./Special:BookSources/978-92-9083-095-5). [Archived](https://web.archive.org/web/20180207110306/https://cds.cern.ch/record/400313/files/p21.pdf) (PDF) from the original on 2018-02-07.
7. [↑](./Computer_vision#cite_ref-Sonka-Hlavac-Boyle-2008_7-0) Milan Sonka; Vaclav Hlavac; Roger Boyle (2008). *Image Processing, Analysis, and Machine Vision*. Thomson. [ISBN](./ISBN_(identifier)) [978-0-495-08252-1](./Special:BookSources/978-0-495-08252-1).
8. [↑](./Computer_vision#cite_ref-bmva_8-0) [http://www.bmva.org/visionoverview](http://www.bmva.org/visionoverview) [Archived](https://web.archive.org/web/20170216180225/http://www.bmva.org/visionoverview) 2017-02-16 at the [Wayback Machine](./Wayback_Machine) The British Machine Vision Association and Society for Pattern Recognition Retrieved February 20, 2017
9. [↑](./Computer_vision#cite_ref-9) Murphy, Mike (13 April 2017). ["Star Trek's "tricorder" medical scanner just got closer to becoming a reality"](https://qz.com/957285/star-treks-tricorder-handheld-medical-scanner-just-got-closer-to-becoming-a-reality/). [Archived](https://web.archive.org/web/20170702123646/https://qz.com/957285/star-treks-tricorder-handheld-medical-scanner-just-got-closer-to-becoming-a-reality/) from the original on 2 July 2017. Retrieved 18 July 2017.
10. [↑](./Computer_vision#cite_ref-davies5_10-0) *Computer Vision* Principles, algorithms, Applications, Learning   5th Edition by E.R. Davies Academic Press, Elsevier 2018 ISBN 978-0-12-809284-2
11. [1](./Computer_vision#cite_ref-Szeliski2010_11-0) [2](./Computer_vision#cite_ref-Szeliski2010_11-1) [3](./Computer_vision#cite_ref-Szeliski2010_11-2) [4](./Computer_vision#cite_ref-Szeliski2010_11-3) Richard Szeliski (30 September 2010). [*Computer Vision: Algorithms and Applications*](https://books.google.com/books?id=bXzAlkODwa8C). Springer Science & Business Media. pp. 10–16. [ISBN](./ISBN_(identifier)) [978-1-84882-935-0](./Special:BookSources/978-1-84882-935-0).
12. [↑](./Computer_vision#cite_ref-12) Sejnowski, Terrence J. (2018). *The deep learning revolution*. Cambridge, Massachusetts London, England: The MIT Press. p. 28. [ISBN](./ISBN_(identifier)) [978-0-262-03803-4](./Special:BookSources/978-0-262-03803-4).
13. [↑](./Computer_vision#cite_ref-Seymour1966_13-0) [Papert, Seymour](./Seymour_Papert) (1966-07-01). "The Summer Vision Project". *MIT AI Memos (1959 - 2004)*. [hdl](./Hdl_(identifier)):[1721.1/6125](https://hdl.handle.net/1721.1%2F6125).
14. [↑](./Computer_vision#cite_ref-Boden2006_14-0) Margaret Ann Boden (2006). [*Mind as Machine: A History of Cognitive Science*](https://books.google.com/books?id=yRyETy43AdQC). Clarendon Press. p. 781. [ISBN](./ISBN_(identifier)) [978-0-19-954316-8](./Special:BookSources/978-0-19-954316-8).
15. [↑](./Computer_vision#cite_ref-Kanade20122_15-0) Takeo Kanade (6 December 2012). [*Three-Dimensional Machine Vision*](https://books.google.com/books?id=e0jtBwAAQBAJ&pg=PA191). Springer Science & Business Media. [ISBN](./ISBN_(identifier)) [978-1-4613-1981-8](./Special:BookSources/978-1-4613-1981-8).
16. [↑](./Computer_vision#cite_ref-Sebe2005_16-0) Nicu Sebe; Ira Cohen; Ashutosh Garg; Thomas S. Huang (3 June 2005). [*Machine Learning in Computer Vision*](https://books.google.com/books?id=lemw2Rhr_PEC). Springer Science & Business Media. [ISBN](./ISBN_(identifier)) [978-1-4020-3274-5](./Special:BookSources/978-1-4020-3274-5).
17. [↑](./Computer_vision#cite_ref-Freeman2008_17-0) William Freeman; Pietro Perona; Bernhard Scholkopf (2008). ["Guest Editorial: Machine Learning for Computer Vision"](https://doi.org/10.1007%2Fs11263-008-0127-7). *International Journal of Computer Vision*. **77** (1): 1. [doi](./Doi_(identifier)):[10.1007/s11263-008-0127-7](https://doi.org/10.1007%2Fs11263-008-0127-7). [hdl](./Hdl_(identifier)):[21.11116/0000-0003-30FB-C](https://hdl.handle.net/21.11116%2F0000-0003-30FB-C). [ISSN](./ISSN_(identifier)) [1573-1405](https://search.worldcat.org/issn/1573-1405).
18. [↑](./Computer_vision#cite_ref-NatureBengio_18-0) LeCun, Yann; Bengio, Yoshua; Hinton, Geoffrey (2015). ["Deep Learning"](https://hal.science/hal-04206682/file/Lecun2015.pdf) (PDF). *Nature*. **521** (7553): 436–444. [Bibcode](./Bibcode_(identifier)):[2015Natur.521..436L](https://ui.adsabs.harvard.edu/abs/2015Natur.521..436L). [doi](./Doi_(identifier)):[10.1038/nature14539](https://doi.org/10.1038%2Fnature14539). [PMID](./PMID_(identifier)) [26017442](https://pubmed.ncbi.nlm.nih.gov/26017442). [S2CID](./S2CID_(identifier)) [3074096](https://api.semanticscholar.org/CorpusID:3074096).
19. [↑](./Computer_vision#cite_ref-19) Ilg, Eddy; Mayer, Nikolaus; Saikia, Tonmoy; Keuper, Margret; Dosovitskiy, Alexey; Brox, Thomas (2016). "FlowNet 2.0: Evolution of Optical Flow Estimation with Deep Networks". [arXiv](./ArXiv_(identifier)):[1612.01925](https://arxiv.org/abs/1612.01925) [[cs.CV](https://arxiv.org/archive/cs.CV)].
20. [↑](./Computer_vision#cite_ref-20) Jiao, Licheng; Zhang, Fan; Liu, Fang; Yang, Shuyuan; Li, Lingling; Feng, Zhixi; [Qu, Rong](./Rong_Qu) (2019). ["A Survey of Deep Learning-Based Object Detection"](https://doi.org/10.1109%2FACCESS.2019.2939201). *IEEE Access*. **7**: 128837–128868. [arXiv](./ArXiv_(identifier)):[1907.09408](https://arxiv.org/abs/1907.09408). [Bibcode](./Bibcode_(identifier)):[2019IEEEA...7l8837J](https://ui.adsabs.harvard.edu/abs/2019IEEEA...7l8837J). [doi](./Doi_(identifier)):[10.1109/ACCESS.2019.2939201](https://doi.org/10.1109%2FACCESS.2019.2939201). [S2CID](./S2CID_(identifier)) [198147317](https://api.semanticscholar.org/CorpusID:198147317).
21. [↑](./Computer_vision#cite_ref-21) Ferrie, C.; Kaiser, S. (2019). *Neural Networks for Babies*. Sourcebooks. [ISBN](./ISBN_(identifier)) [978-1-4926-7120-6](./Special:BookSources/978-1-4926-7120-6).
22. [1](./Computer_vision#cite_ref-TextbookP1_22-0) [2](./Computer_vision#cite_ref-TextbookP1_22-1) Steger, Carsten; Markus Ulrich; Christian Wiedemann (2018). [*Machine Vision Algorithms and Applications*](https://books.google.com/books?id=tppFDwAAQBAJ) (2nd ed.). Weinheim: [Wiley-VCH](./Wiley-VCH). p. 1. [ISBN](./ISBN_(identifier)) [978-3-527-41365-2](./Special:BookSources/978-3-527-41365-2). [Archived](https://web.archive.org/web/20230315180825/https://books.google.com/books?id=tppFDwAAQBAJ) from the original on 2023-03-15. Retrieved 2018-01-30.
23. [↑](./Computer_vision#cite_ref-23) Murray, Don, and Cullen Jennings. "[Stereo vision-based mapping and navigation for mobile robots](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.65.6725&rep=rep1&type=pdf) [Archived](https://web.archive.org/web/20201031141636/http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.65.6725&rep=rep1&type=pdf) 2020-10-31 at the [Wayback Machine](./Wayback_Machine)." Proceedings of International Conference on Robotics and Automation. Vol. 2. IEEE, 1997.
24. [↑](./Computer_vision#cite_ref-24) Andrade, Norberto Almeida. ["Computational Vision and Business Intelligence in the Beauty Segment - An Analysis through Instagram"](https://web.archive.org/web/20240311082943/http://jmm-net.com/journals/jmm/Vol_7_No_2_December_2019/2.pdf) (PDF). *Journal of Marketing Management*. American Research Institute for Policy Development. Archived from the original on March 11, 2024. Retrieved 11 March 2024.
25. [1](./Computer_vision#cite_ref-3DVAE_25-0) [2](./Computer_vision#cite_ref-3DVAE_25-1) [3](./Computer_vision#cite_ref-3DVAE_25-2) Soltani, A. A.; Huang, H.; Wu, J.; Kulkarni, T. D.; Tenenbaum, J. B. (2017). "Synthesizing 3D Shapes via Modeling Multi-view Depth Maps and Silhouettes with Deep Generative Networks". *2017 IEEE Conference on Computer Vision and Pattern Recognition (CVPR)*. pp. 1511–1519. [doi](./Doi_(identifier)):[10.1109/CVPR.2017.269](https://doi.org/10.1109%2FCVPR.2017.269). [hdl](./Hdl_(identifier)):[1721.1/126644](https://hdl.handle.net/1721.1%2F126644). [ISBN](./ISBN_(identifier)) [978-1-5386-0457-1](./Special:BookSources/978-1-5386-0457-1). [S2CID](./S2CID_(identifier)) [31373273](https://api.semanticscholar.org/CorpusID:31373273).
26. [↑](./Computer_vision#cite_ref-NASAarticle_26-0) Turek, Fred (June 2011). "Machine Vision Fundamentals, How to Make Robots See". *NASA Tech Briefs Magazine*. **35** (6). pages 60–62
27. [↑](./Computer_vision#cite_ref-27) ["The Future of Automated Random Bin Picking"](https://www.robots.com/blog/viewing/the-future-of-automated-random-bin-picking). [Archived](https://web.archive.org/web/20180111164947/https://www.robots.com/blog/viewing/the-future-of-automated-random-bin-picking) from the original on 2018-01-11. Retrieved 2018-01-10.
28. [↑](./Computer_vision#cite_ref-28) Esteva, Andre; Chou, Katherine; Yeung, Serena; Naik, Nikhil; Madani, Ali; Mottaghi, Ali; Liu, Yun; Topol, Eric; Dean, Jeff; Socher, Richard (2021-01-08). ["Deep learning-enabled medical computer vision"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7794558). *npj Digital Medicine*. **4** (1): 5. [doi](./Doi_(identifier)):[10.1038/s41746-020-00376-2](https://doi.org/10.1038%2Fs41746-020-00376-2). [ISSN](./ISSN_(identifier)) [2398-6352](https://search.worldcat.org/issn/2398-6352). [PMC](./PMC_(identifier)) [7794558](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7794558). [PMID](./PMID_(identifier)) [33420381](https://pubmed.ncbi.nlm.nih.gov/33420381).
29. [↑](./Computer_vision#cite_ref-29) Chervyakov, N. I.; Lyakhov, P. A.; Deryabin, M. A.; Nagornov, N. N.; Valueva, M. V.; Valuev, G. V. (2020). "Residue Number System-Based Solution for Reducing the Hardware Cost of a Convolutional Neural Network". *Neurocomputing*. **407**: 439–453. [doi](./Doi_(identifier)):[10.1016/j.neucom.2020.04.018](https://doi.org/10.1016%2Fj.neucom.2020.04.018). [S2CID](./S2CID_(identifier)) [219470398](https://api.semanticscholar.org/CorpusID:219470398). Convolutional neural networks (CNNs) represent deep learning architectures that are currently used in a wide range of applications, including computer vision, speech recognition, identification of albuminous sequences in bioinformatics, production control, time series analysis in finance, and many others.
30. [↑](./Computer_vision#cite_ref-30) Wäldchen, Jana; Mäder, Patrick (2017-01-07). ["Plant Species Identification Using Computer Vision Techniques: A Systematic Literature Review"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6003396). *Archives of Computational Methods in Engineering*. **25** (2): 507–543. [doi](./Doi_(identifier)):[10.1007/s11831-016-9206-z](https://doi.org/10.1007%2Fs11831-016-9206-z). [ISSN](./ISSN_(identifier)) [1134-3060](https://search.worldcat.org/issn/1134-3060). [PMC](./PMC_(identifier)) [6003396](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6003396). [PMID](./PMID_(identifier)) [29962832](https://pubmed.ncbi.nlm.nih.gov/29962832).
31. [↑](./Computer_vision#cite_ref-31) Aghamohammadesmaeilketabforoosh, Kimia; Nikan, Soodeh; Antonini, Giorgio; Pearce, Joshua M. (January 2024). ["Optimizing Strawberry Disease and Quality Detection with Vision Transformers and Attention-Based Convolutional Neural Networks"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11202458). *Foods*. **13** (12): 1869. [doi](./Doi_(identifier)):[10.3390/foods13121869](https://doi.org/10.3390%2Ffoods13121869). [ISSN](./ISSN_(identifier)) [2304-8158](https://search.worldcat.org/issn/2304-8158). [PMC](./PMC_(identifier)) [11202458](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11202458). [PMID](./PMID_(identifier)) [38928810](https://pubmed.ncbi.nlm.nih.gov/38928810).
32. [↑](./Computer_vision#cite_ref-32) ["New AI model developed at Western detects strawberry diseases, takes aim at waste"](https://www.ctvnews.ca/london/article/new-ai-model-developed-at-western-detects-strawberry-diseases-takes-aim-at-waste/). *London*. 2024-09-13. Retrieved 2024-09-19.
33. [↑](./Computer_vision#cite_ref-33) ["Applications of Computer Vision"](https://www.geeksforgeeks.org/applications-of-computer-vision/). *GeeksforGeeks*. 2020-06-30. Retrieved 2025-04-27.
34. [↑](./Computer_vision#cite_ref-34) ["Global Industrial Machine Vision Market Growth Analysis - Size and Forecast 2024 - 2028"](https://www.technavio.com/report/industrial-machine-vision-market-analysis). *www.technavio.com*. Retrieved 2025-05-14.
35. [↑](./Computer_vision#cite_ref-35) Laviola, Erin. ["What Is Computer Vision and How Is It Being Used in Healthcare?"](https://healthtechmagazine.net/article/2025/03/what-is-computer-vision-in-healthcare-perfcon). *HealthTech*. Retrieved 2025-05-14.
36. [↑](./Computer_vision#cite_ref-36) ["Computer Vision - Artificial intelligence in military market outlook"](https://www.grandviewresearch.com/horizon/statistics/artificial-intelligence-in-military-market/technology/computer-vision/global). *www.grandviewresearch.com*. Retrieved 2025-05-14.
37. [↑](./Computer_vision#cite_ref-37) Li, Mengfang; Jiang, Yuanyuan; Zhang, Yanzhou; Zhu, Haisheng (2023). ["Medical image analysis using deep learning algorithms"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10662291). *Frontiers in Public Health*. **11** 1273253. [Bibcode](./Bibcode_(identifier)):[2023FrPH...1173253L](https://ui.adsabs.harvard.edu/abs/2023FrPH...1173253L). [doi](./Doi_(identifier)):[10.3389/fpubh.2023.1273253](https://doi.org/10.3389%2Ffpubh.2023.1273253). [ISSN](./ISSN_(identifier)) [2296-2565](https://search.worldcat.org/issn/2296-2565). [PMC](./PMC_(identifier)) [10662291](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10662291). [PMID](./PMID_(identifier)) [38026291](https://pubmed.ncbi.nlm.nih.gov/38026291).
38. [1](./Computer_vision#cite_ref-Davies-2005_38-0) [2](./Computer_vision#cite_ref-Davies-2005_38-1) [3](./Computer_vision#cite_ref-Davies-2005_38-2) [4](./Computer_vision#cite_ref-Davies-2005_38-3) [5](./Computer_vision#cite_ref-Davies-2005_38-4) [6](./Computer_vision#cite_ref-Davies-2005_38-5) E. Roy Davies (2005). *Machine Vision: Theory, Algorithms, Practicalities*. Morgan Kaufmann. [ISBN](./ISBN_(identifier)) [978-0-12-206093-9](./Special:BookSources/978-0-12-206093-9).
39. [↑](./Computer_vision#cite_ref-:0_39-0) Ando, Mitsuhito; Takei, Toshinobu; Mochiyama, Hiromi (2020-03-03). ["Rubber artificial skin layer with flexible structure for shape estimation of micro-undulation surfaces"](https://doi.org/10.1186%2Fs40648-020-00159-0). *ROBOMECH Journal*. **7** (1): 11. [doi](./Doi_(identifier)):[10.1186/s40648-020-00159-0](https://doi.org/10.1186%2Fs40648-020-00159-0). [ISSN](./ISSN_(identifier)) [2197-4225](https://search.worldcat.org/issn/2197-4225).
40. [↑](./Computer_vision#cite_ref-:1_40-0) Choi, Seung-hyun; Tahara, Kenji (2020-03-12). ["Dexterous object manipulation by a multi-fingered robotic hand with visual-tactile fingertip sensors"](https://doi.org/10.1186%2Fs40648-020-00162-5). *ROBOMECH Journal*. **7** (1): 14. [doi](./Doi_(identifier)):[10.1186/s40648-020-00162-5](https://doi.org/10.1186%2Fs40648-020-00162-5). [ISSN](./ISSN_(identifier)) [2197-4225](https://search.worldcat.org/issn/2197-4225).
41. [↑](./Computer_vision#cite_ref-41) Garg, Hitendra (2020-02-29). "Drowsiness Detection of a Driver using Conventional Computer Vision Application". *2020 International Conference on Power Electronics & IoT Applications in Renewable Energy and its Control (PARC)*. pp. 50–53. [doi](./Doi_(identifier)):[10.1109/PARC49193.2020.236556](https://doi.org/10.1109%2FPARC49193.2020.236556). [ISBN](./ISBN_(identifier)) [978-1-7281-6575-2](./Special:BookSources/978-1-7281-6575-2). [S2CID](./S2CID_(identifier)) [218564267](https://api.semanticscholar.org/CorpusID:218564267).
42. [↑](./Computer_vision#cite_ref-42) Hasan, Fudail; Kashevnik, Alexey (2021-05-14). ["State-of-the-Art Analysis of Modern Drowsiness Detection Algorithms Based on Computer Vision"](https://ieeexplore.ieee.org/document/9435480). *2021 29th Conference of Open Innovations Association (FRUCT)*. pp. 141–149. [doi](./Doi_(identifier)):[10.23919/FRUCT52173.2021.9435480](https://doi.org/10.23919%2FFRUCT52173.2021.9435480). [ISBN](./ISBN_(identifier)) [978-952-69244-5-8](./Special:BookSources/978-952-69244-5-8). [S2CID](./S2CID_(identifier)) [235207036](https://api.semanticscholar.org/CorpusID:235207036). [Archived](https://web.archive.org/web/20220627061552/https://ieeexplore.ieee.org/document/9435480/) from the original on 2022-06-27. Retrieved 2022-11-06.
43. [↑](./Computer_vision#cite_ref-43) Balasundaram, A; Ashokkumar, S; Kothandaraman, D; kora, SeenaNaik; Sudarshan, E; Harshaverdhan, A (2020-12-01). ["Computer vision based fatigue detection using facial parameters"](https://doi.org/10.1088%2F1757-899x%2F981%2F2%2F022005). *IOP Conference Series: Materials Science and Engineering*. **981** (2) 022005. [Bibcode](./Bibcode_(identifier)):[2020MS&E..981b2005B](https://ui.adsabs.harvard.edu/abs/2020MS&E..981b2005B). [doi](./Doi_(identifier)):[10.1088/1757-899x/981/2/022005](https://doi.org/10.1088%2F1757-899x%2F981%2F2%2F022005). [ISSN](./ISSN_(identifier)) [1757-899X](https://search.worldcat.org/issn/1757-899X). [S2CID](./S2CID_(identifier)) [230639179](https://api.semanticscholar.org/CorpusID:230639179).
44. [1](./Computer_vision#cite_ref-BruijningVisser2018_44-0) [2](./Computer_vision#cite_ref-BruijningVisser2018_44-1) Bruijning, Marjolein; Visser, Marco D.; Hallmann, Caspar A.; Jongejans, Eelke; Golding, Nick (2018). ["trackdem: Automated particle tracking to obtain population counts and size distributions from videos in r"](https://doi.org/10.1111%2F2041-210X.12975). *Methods in Ecology and Evolution*. **9** (4): 965–973. [Bibcode](./Bibcode_(identifier)):[2018MEcEv...9..965B](https://ui.adsabs.harvard.edu/abs/2018MEcEv...9..965B). [doi](./Doi_(identifier)):[10.1111/2041-210X.12975](https://doi.org/10.1111%2F2041-210X.12975). [hdl](./Hdl_(identifier)):[2066/184075](https://hdl.handle.net/2066%2F184075). [ISSN](./ISSN_(identifier)) [2041-210X](https://search.worldcat.org/issn/2041-210X).
45. [↑](./Computer_vision#cite_ref-45) Quamer, Amanullah; Asgari, Nima; Pearce, Joshua M (2026-06-01). ["Two-stage deep learning model for non-destructive leaf counting in tomato crops"](https://www.sciencedirect.com/science/article/pii/S0168169926003121). *Computers and Electronics in Agriculture*. **247** 111717. [doi](./Doi_(identifier)):[10.1016/j.compag.2026.111717](https://doi.org/10.1016%2Fj.compag.2026.111717). [ISSN](./ISSN_(identifier)) [0168-1699](https://search.worldcat.org/issn/0168-1699).
46. [↑](./Computer_vision#cite_ref-Forsyth-Ponce-2003_46-0) David A. Forsyth; Jean Ponce (2003). *Computer Vision, A Modern Approach*. Prentice Hall. [ISBN](./ISBN_(identifier)) [978-0-13-085198-7](./Special:BookSources/978-0-13-085198-7).
47. [↑](./Computer_vision#cite_ref-Forsyth2012_47-0) Forsyth, David; Ponce, Jean (2012). *Computer vision: a modern approach*. Pearson.
48. [1](./Computer_vision#cite_ref-:2_48-0) [2](./Computer_vision#cite_ref-:2_48-1) Russakovsky, Olga; Deng, Jia; Su, Hao; Krause, Jonathan; Satheesh, Sanjeev; Ma, Sean; Huang, Zhiheng; Karpathy, Andrej; Khosla, Aditya; Bernstein, Michael; Berg, Alexander C. (December 2015). ["ImageNet Large Scale Visual Recognition Challenge"](http://link.springer.com/10.1007/s11263-015-0816-y). *International Journal of Computer Vision*. **115** (3): 211–252. [arXiv](./ArXiv_(identifier)):[1409.0575](https://arxiv.org/abs/1409.0575). [doi](./Doi_(identifier)):[10.1007/s11263-015-0816-y](https://doi.org/10.1007%2Fs11263-015-0816-y). [hdl](./Hdl_(identifier)):[1721.1/104944](https://hdl.handle.net/1721.1%2F104944). [ISSN](./ISSN_(identifier)) [0920-5691](https://search.worldcat.org/issn/0920-5691). [S2CID](./S2CID_(identifier)) [2930547](https://api.semanticscholar.org/CorpusID:2930547). [Archived](https://web.archive.org/web/20230315180822/https://link.springer.com/article/10.1007/s11263-015-0816-y) from the original on 2023-03-15. Retrieved 2020-11-20.
49. [↑](./Computer_vision#cite_ref-49) Quinn, Arthur (2022-10-09). ["AI Image Recognition: Inevitable Trending of Modern Lifestyle"](https://topten.ai/ai-image-recognition/). *TopTen.ai*. [Archived](https://web.archive.org/web/20221202063116/https://topten.ai/ai-image-recognition/) from the original on 2022-12-02. Retrieved 2022-12-23.
50. [↑](./Computer_vision#cite_ref-50) Barrett, Lisa Feldman; Adolphs, Ralph; Marsella, Stacy; Martinez, Aleix M.; Pollak, Seth D. (July 2019). ["Emotional Expressions Reconsidered: Challenges to Inferring Emotion From Human Facial Movements"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6640856). *Psychological Science in the Public Interest*. **20** (1): 1–68. [doi](./Doi_(identifier)):[10.1177/1529100619832930](https://doi.org/10.1177%2F1529100619832930). [ISSN](./ISSN_(identifier)) [1529-1006](https://search.worldcat.org/issn/1529-1006). [PMC](./PMC_(identifier)) [6640856](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6640856). [PMID](./PMID_(identifier)) [31313636](https://pubmed.ncbi.nlm.nih.gov/31313636).
51. [↑](./Computer_vision#cite_ref-51) A. Maity (2015). "Improvised Salient Object Detection and Manipulation". [arXiv](./ArXiv_(identifier)):[1511.02999](https://arxiv.org/abs/1511.02999) [[cs.CV](https://arxiv.org/archive/cs.CV)].
52. [↑](./Computer_vision#cite_ref-52) Barghout, Lauren. "[Visual Taxometric Approach to Image Segmentation Using Fuzzy-Spatial Taxon Cut Yields Contextually Relevant Regions](http://www.lirmm.fr/~lafourcade/pub/IPMU2014/papers/0443/04430163.pdf) [Archived](https://web.archive.org/web/20181114100658/http://www.lirmm.fr/~lafourcade/pub/IPMU2014/papers/0443/04430163.pdf) 2018-11-14 at the [Wayback Machine](./Wayback_Machine)." Information Processing and Management of Uncertainty in Knowledge-Based Systems. Springer International Publishing, 2014.
53. [↑](./Computer_vision#cite_ref-Liu_Wang_Hua_Zhang_2018_pp._5840–5853_53-0) Liu, Ziyi; Wang, Le; Hua, Gang; Zhang, Qilin; Niu, Zhenxing; Wu, Ying; Zheng, Nanning (2018). ["Joint Video Object Discovery and Segmentation by Coupled Dynamic Markov Networks"](https://web.archive.org/web/20180907032435/https://qilin-zhang.github.io/_pages/pdfs/Joint_Video_Object_Discovery_and_Segmentation_by_Coupled_Dynamic_Markov_Networks.pdf) (PDF). *IEEE Transactions on Image Processing*. **27** (12): 5840–5853. [Bibcode](./Bibcode_(identifier)):[2018ITIP...27.5840L](https://ui.adsabs.harvard.edu/abs/2018ITIP...27.5840L). [doi](./Doi_(identifier)):[10.1109/tip.2018.2859622](https://doi.org/10.1109%2Ftip.2018.2859622). [ISSN](./ISSN_(identifier)) [1057-7149](https://search.worldcat.org/issn/1057-7149). [PMID](./PMID_(identifier)) [30059300](https://pubmed.ncbi.nlm.nih.gov/30059300). [S2CID](./S2CID_(identifier)) [51867241](https://api.semanticscholar.org/CorpusID:51867241). Archived from [the original](https://qilin-zhang.github.io/_pages/pdfs/Joint_Video_Object_Discovery_and_Segmentation_by_Coupled_Dynamic_Markov_Networks.pdf) (PDF) on 2018-09-07. Retrieved 2018-09-14.
54. [↑](./Computer_vision#cite_ref-Wang_Duan_Zhang_Niu_p=1657_54-0) Wang, Le; Duan, Xuhuan; Zhang, Qilin; Niu, Zhenxing; Hua, Gang; Zheng, Nanning (2018-05-22). ["Segment-Tube: Spatio-Temporal Action Localization in Untrimmed Videos with Per-Frame Segmentation"](https://qilin-zhang.github.io/_pages/pdfs/Segment-Tube_Spatio-Temporal_Action_Localization_in_Untrimmed_Videos_with_Per-Frame_Segmentation.pdf) (PDF). *Sensors*. **18** (5): 1657. [Bibcode](./Bibcode_(identifier)):[2018Senso..18.1657W](https://ui.adsabs.harvard.edu/abs/2018Senso..18.1657W). [doi](./Doi_(identifier)):[10.3390/s18051657](https://doi.org/10.3390%2Fs18051657). [ISSN](./ISSN_(identifier)) [1424-8220](https://search.worldcat.org/issn/1424-8220). [PMC](./PMC_(identifier)) [5982167](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5982167). [PMID](./PMID_(identifier)) [29789447](https://pubmed.ncbi.nlm.nih.gov/29789447). [Archived](https://web.archive.org/web/20180907110146/https://qilin-zhang.github.io/_pages/pdfs/Segment-Tube_Spatio-Temporal_Action_Localization_in_Untrimmed_Videos_with_Per-Frame_Segmentation.pdf) (PDF) from the original on 2018-09-07.
55. [↑](./Computer_vision#cite_ref-55) Shapiro, Stuart C. (1992). *Encyclopedia of Artificial Intelligence, Volume 1*. New York: John Wiley & Sons, Inc. pp. 643–646. [ISBN](./ISBN_(identifier)) [978-0-471-50306-4](./Special:BookSources/978-0-471-50306-4).
56. [↑](./Computer_vision#cite_ref-56) Kagami, Shingo (2010). "High-speed vision systems and projectors for real-time perception of the world". *2010 IEEE Computer Society Conference on Computer Vision and Pattern Recognition - Workshops*. Vol. 2010. pp. 100–107. [doi](./Doi_(identifier)):[10.1109/CVPRW.2010.5543776](https://doi.org/10.1109%2FCVPRW.2010.5543776). [ISBN](./ISBN_(identifier)) [978-1-4244-7029-7](./Special:BookSources/978-1-4244-7029-7). [S2CID](./S2CID_(identifier)) [14111100](https://api.semanticscholar.org/CorpusID:14111100).
57. [↑](./Computer_vision#cite_ref-the_rise_of_VPUs_57-0) Seth Colaner (January 3, 2016). ["A Third Type Of Processor For VR/AR: Movidius' Myriad 2 VPU"](http://www.tomshardware.com/news/movidiud-myriad2-vpu-vision-processing-vr,30850.html). *www.tomshardware.com*. [Archived](https://web.archive.org/web/20230315180744/https://www.tomshardware.com/news/movidiud-myriad2-vpu-vision-processing-vr,30850.html) from the original on March 15, 2023. Retrieved May 3, 2016.

 

## Further reading

 
- James E. Dobson (2023). [*The Birth of Computer Vision*](https://www.upress.umn.edu/book-division/books/the-birth-of-computer-vision). University of Minnesota Press. [ISBN](./ISBN_(identifier)) [978-1-5179-1421-9](./Special:BookSources/978-1-5179-1421-9).
- [David Marr](./David_Marr_(neuroscientist)) (1982). [*Vision*](https://archive.org/details/vision00davi). W. H. Freeman and Company. [ISBN](./ISBN_(identifier)) [978-0-7167-1284-8](./Special:BookSources/978-0-7167-1284-8).
- Azriel Rosenfeld; Avinash Kak (1982). *Digital Picture Processing*. Academic Press. [ISBN](./ISBN_(identifier)) [978-0-12-597301-4](./Special:BookSources/978-0-12-597301-4).
- Barghout, Lauren; Lawrence W. Lee (2003). [*Perceptual information processing system*](https://archive.org/details/robotvision0000horn). U.S. Patent Application 10/618,543. [ISBN](./ISBN_(identifier)) [978-0-262-08159-7](./Special:BookSources/978-0-262-08159-7).
- [Berthold K.P. Horn](./Berthold_K.P._Horn) (1986). [*Robot Vision*](https://archive.org/details/robotvision0000horn). MIT Press. [ISBN](./ISBN_(identifier)) [978-0-262-08159-7](./Special:BookSources/978-0-262-08159-7).
- Michael C. Fairhurst (1988). *Computer Vision for robotic systems*. Prentice Hall. [ISBN](./ISBN_(identifier)) [978-0-13-166919-2](./Special:BookSources/978-0-13-166919-2).
- [Olivier Faugeras](./Olivier_Faugeras) (1993). *Three-Dimensional Computer Vision, A Geometric Viewpoint*. MIT Press. [ISBN](./ISBN_(identifier)) [978-0-262-06158-2](./Special:BookSources/978-0-262-06158-2).
- Tony Lindeberg (1994). [*Scale-Space Theory in Computer Vision*](http://www.nada.kth.se/~tony/book.html). Springer. [ISBN](./ISBN_(identifier)) [978-0-7923-9418-1](./Special:BookSources/978-0-7923-9418-1).
- James L. Crowley; Henrik I. Christensen, eds. (1995). *Vision as Process*. Springer-Verlag. [ISBN](./ISBN_(identifier)) [978-3-540-58143-7](./Special:BookSources/978-3-540-58143-7).
- Gösta H. Granlund; Hans Knutsson (1995). *Signal Processing for Computer Vision*. Kluwer Academic Publisher. [ISBN](./ISBN_(identifier)) [978-0-7923-9530-0](./Special:BookSources/978-0-7923-9530-0).
- Reinhard Klette; Karsten Schluens; Andreas Koschan (1998). [*Computer Vision – Three-Dimensional Data from Images*](https://www.cs.auckland.ac.nz/~rklette/Books/SpringerCV98/Springer98.html). Springer, Singapore. [ISBN](./ISBN_(identifier)) [978-981-3083-71-4](./Special:BookSources/978-981-3083-71-4).
- Emanuele Trucco; Alessandro Verri (1998). [*Introductory Techniques for 3-D Computer Vision*](https://archive.org/details/introductorytech0000truc). Prentice Hall. [ISBN](./ISBN_(identifier)) [978-0-13-261108-4](./Special:BookSources/978-0-13-261108-4).
- Bernd Jähne (2002). *Digital Image Processing*. Springer. [ISBN](./ISBN_(identifier)) [978-3-540-67754-3](./Special:BookSources/978-3-540-67754-3).
- Richard Hartley and [Andrew Zisserman](./Andrew_Zisserman) (2003). *Multiple View Geometry in Computer Vision*. Cambridge University Press. [ISBN](./ISBN_(identifier)) [978-0-521-54051-3](./Special:BookSources/978-0-521-54051-3).
- Gérard Medioni; [Sing Bing Kang](./Sing_Bing_Kang) (2004). *Emerging Topics in Computer Vision*. Prentice Hall. [ISBN](./ISBN_(identifier)) [978-0-13-101366-7](./Special:BookSources/978-0-13-101366-7).
- R. Fisher; K Dawson-Howe; A. Fitzgibbon; C. Robertson; E. Trucco (2005). *Dictionary of Computer Vision and Image Processing*. John Wiley. [ISBN](./ISBN_(identifier)) [978-0-470-01526-1](./Special:BookSources/978-0-470-01526-1).
- [Nikos Paragios](./Nikos_Paragios) and Yunmei Chen and [Olivier Faugeras](./Olivier_Faugeras) (2005). [*Handbook of Mathematical Models in Computer Vision*](http://www.mas.ecp.fr/vision/Personnel/nikos/paragios-chen-faugeras/). Springer. [ISBN](./ISBN_(identifier)) [978-0-387-26371-7](./Special:BookSources/978-0-387-26371-7).
- Wilhelm Burger; Mark J. Burge (2007). [*Digital Image Processing: An Algorithmic Approach Using Java*](https://web.archive.org/web/20140517114947/http://imagingbook.com/). [Springer](./Springer_Science+Business_Media). [ISBN](./ISBN_(identifier)) [978-1-84628-379-6](./Special:BookSources/978-1-84628-379-6). Archived from [the original](http://www.imagingbook.com/) on 2014-05-17. Retrieved 2007-06-13.
- Pedram Azad; Tilo Gockel; Rüdiger Dillmann (2008). [*Computer Vision – Principles and Practice*](https://ivt.sourceforge.net/book.html). Elektor International Media BV. [ISBN](./ISBN_(identifier)) [978-0-905705-71-2](./Special:BookSources/978-0-905705-71-2).
- Richard Szeliski (2010). [*Computer Vision: Algorithms and Applications*](http://szeliski.org/Book/). Springer-Verlag. [ISBN](./ISBN_(identifier)) [978-1-84882-934-3](./Special:BookSources/978-1-84882-934-3).
- J. R. Parker (2011). *Algorithms for Image Processing and Computer Vision* (2nd ed.). Wiley. [ISBN](./ISBN_(identifier)) [978-0-470-64385-3](./Special:BookSources/978-0-470-64385-3).
- Richard J. Radke (2013). *Computer Vision for Visual Effects*. Cambridge University Press. [ISBN](./ISBN_(identifier)) [978-0-521-76687-6](./Special:BookSources/978-0-521-76687-6).
- Nixon, Mark; Aguado, Alberto (2019). *Feature Extraction and Image Processing for Computer Vision* (4th ed.). Academic Press. [ISBN](./ISBN_(identifier)) [978-0-12-814976-8](./Special:BookSources/978-0-12-814976-8).

 

## External links

 
- [USC Iris computer vision conference list](https://sites.usc.edu/iris-cvlab/)
- [Computer vision papers on the web](http://www.cvpapers.com/index.html) – a complete list of papers of the most relevant computer vision conferences.
- [Computer Vision Online](http://www.computervisiononline.com/) [Archived](https://web.archive.org/web/20111130184909/http://www.computervisiononline.com/) 2011-11-30 at the [Wayback Machine](./Wayback_Machine) – news, source code, datasets and job offers related to computer vision
- [CVonline](http://homepages.inf.ed.ac.uk/rbf/CVonline/) – Bob Fisher's Compendium of Computer Vision.
- [British Machine Vision Association](https://britishmachinevisionassociation.github.io/) – supporting computer vision research within the UK via the BMVC and MIUA conferences, *Annals of the [BMVA](./BMVA?action=edit&redlink=1)* (open-source journal), [BMVA Summer School](./BMVA_Summer_School) and one-day meetings
- [Computer Vision Container, Joe Hoeller GitHub:](https://github.com/joehoeller/NVIDIA-GPU-Tensor-Core-Accelerator-PyTorch-OpenCV) Widely adopted open-source container for GPU accelerated computer vision applications. Used by researchers, universities, private companies, as well as the U.S. Gov't.

 
| vteComputer vision |
| --- |
| Categories | DatasetsDigital geometryCommercial systemsFeature detectionGeometryImage sensor technologyLearningMorphologyMotion analysisNoise reduction techniquesRecognition and categorizationResearch infrastructureResearchersSegmentationSoftware |
| Technologies | Computer stereo visionMotion captureObject recognition3D object recognition |
| Applications | 3D reconstruction3D reconstruction from multiple images2D to 3D conversionGaussian splattingNeural radiance fieldShape from focusSimultaneous localization and mappingStructure from motionView synthesisVisual hull4D reconstructionFree viewpoint televisionVolumetric capture3D pose estimationActivity recognitionAudio-visual speech recognitionAutomatic image annotationAutomatic number-plate recognitionAutomated species identificationAugmented realityBioimage informaticsBlob detectionComputer-aided diagnosisContent-based image retrievalReverse image searchEye trackingFace recognitionForeground detectionGesture recognitionImage denoisingImage restorationLandmark detectionMedical image computingObject detectionMoving object detectionPedestrian detectionSmall object detectionOptical character recognitionPose trackingRemote sensingRobotic mappingAutonomous vehiclesVideo browsingVideo content analysisVideo motion analysisVideo surveillanceVideo synopsisVideo tracking | 3D reconstruction | 3D reconstruction from multiple images2D to 3D conversionGaussian splattingNeural radiance fieldShape from focusSimultaneous localization and mappingStructure from motionView synthesisVisual hull4D reconstructionFree viewpoint televisionVolumetric capture |
| 3D reconstruction | 3D reconstruction from multiple images2D to 3D conversionGaussian splattingNeural radiance fieldShape from focusSimultaneous localization and mappingStructure from motionView synthesisVisual hull4D reconstructionFree viewpoint televisionVolumetric capture |
| Main category |

 
| vteDifferentiable computing |
| --- |
| General | Differentiable programmingInformation geometryStatistical manifoldAutomatic differentiationNeuromorphic computingPattern recognitionRicci calculusComputational learning theoryInductive bias |
| Hardware | IPUTPUVPUMemristorSpiNNaker |
| Software libraries | TensorFlowPyTorchKerasscikit-learnTheanoJAXFlux.jlMindSpore |
| PortalsComputer programmingTechnology |

 
| Authority control databases |
| --- |
| National | United StatesFranceBnF dataCzech RepublicIsrael |
| Other | Yale LUX |