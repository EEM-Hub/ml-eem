---
source: sources/wiki-Computer_vision.md
source_url: https://en.wikipedia.org/wiki/Computer_vision
chunk: 4/6
---

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

 


