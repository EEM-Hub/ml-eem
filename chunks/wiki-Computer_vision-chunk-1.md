---
source: sources/wiki-Computer_vision.md
source_url: https://en.wikipedia.org/wiki/Computer_vision
chunk: 1/6
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

 


