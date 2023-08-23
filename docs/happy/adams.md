[ADAMS-based](https://adams.cms.waikato.ac.nz/) framework that can be used
for annotating images using its powerful workflow engine.


# Requirements

* OpenJDK 11+

    * Windows: [adoptium.net/temurin](https://adoptium.net/temurin/releases/?version=11)
    * Debian/Ubuntu: `sudo apt install openjdk-11-jdk`
  
  
# Installation

* Download a snapshot (in ZIP format)

    [adams.cms.waikato.ac.nz/snapshots/happy/](https://adams.cms.waikato.ac.nz/snapshots/happy/)
  
* Unzip the ZIP archive and rename the generated directory to `happy-adams`


# Starting the application 

* Start the user interface with:

  * Windows: `happy-adams\bin\start_gui.bat`
  * Linux: `happy-adams/bin/start_gui.sh`
    

# Available flows

Of the flows that are come with the Happy ADAMS framework, the following ones 
are relevant to the Happy project:

* `adams-imaging-annotate_objects.flow` - generating annotations for 
  object detection (bounding box or polygon)
* `adams-imaging-image_segmentation_annotation.flow` - generating annotations 
  for image segmentation (pixel-level classification)
* `adams-imaging-ext_run-sam.flow` - downloads and runs 
  [SAM (Segment Anything Model)](https://github.com/waikato-datamining/pytorch/tree/master/segment-anything) 
  via Docker (can be used within the above two flows as a separate annotation 
  tool) 


# Tutorials

Instructions on how to use these flows are available from the 
[Applied Deep Learning](https://www.data-mining.co.nz/applied-deep-learning/)
website, specifically:

* [object detection](https://www.data-mining.co.nz/applied-deep-learning/object_detection/annotate/)
* [image segmentation](https://www.data-mining.co.nz/applied-deep-learning/image_segmentation/annotate/)
