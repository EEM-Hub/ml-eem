---
source: sources/wiki-Computer_vision.md
source_url: https://en.wikipedia.org/wiki/Computer_vision
chunk: 3/6
---

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

 


