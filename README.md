# callose-quantification-imagej
Automated ImageJ-based workflow for callose quantification using machine learning segmentation and particle analysis (Custom Macros, Fiji-ImageJ & WEKA segmentation Plugin).
The scripts and trained model provided in this repository are associated with the protocol described in the article *“An optimized protocol to detect callose deposition in soybean lateral roots during fungal infections.”*
## 🔍 Use case
- Measures root area from microscopy images  
- Identifies callose deposits using a trained Weka classifier  
- Automatically counts callose particles  
 
## 📁 Repository structure
- `macros/` – ImageJ macro scripts (`.ijm`)  - parameters can be adjusted as per the need. (Please refer the article)  
- `model/` – Pre-trained classifier for callose detection. Model can be retrained as per the need. (Please refer the article)  
- `example_data/` – Sample images and outputs  

## ▶️ Quick start
1. Open your image in ImageJ and set the scale  
2. Run `Clear Measure Resize.ijm` to crop and measure root area  
3. Load and apply the classifier (`Callose quantification.model`)  
4. Run `Callose analyse particles.ijm` to count callose deposits

# Callose Quantification Protocol (sample output)


### Step 1: Setting the Scale of the Image
![Step 1: Setting the scale](https://github.com/iitj-mpg-lab/callose-quantification-imagej/blob/main/example_data/image1.png?raw=true)

Steps for setting the scale of the image:
* **A.** Open the images saved in .tiff format in ImageJ software and using the line tool draw a line over the scale (the yellow line represents the line drawn over the scale).
* **B.** On the menu bar, select "Analyse" >> "Set Scale" and then make changes accordingly highlighted in red and proceed to "OK".

---

### Step 2: Crop and Measure Root Tissue
![Step 2: Crop and measure](https://github.com/iitj-mpg-lab/callose-quantification-imagej/blob/main/example_data/image2.png?raw=true)

Steps to crop and measure the root tissue in the image:
* **A.** Using a polygon tool, mark a boundary around the root tissue.
* **B.** On the menu bar, select "Plugins" >> "Macros" >> "Run" (`Clear Measure Resize.ijm`).
* **C.** Select the "Clear Measure Resize.ijm" to run the macro.
* **D.** The resulting image after processing along with the area of the cropped root tissue will appear.
* **E & F.** Save the image in .tiff format in "Cropped images" folder.

---

### Step 3: Segmentation of the Cropped Images
![Step 3: Segmentation](https://github.com/iitj-mpg-lab/callose-quantification-imagej/blob/main/example_data/image3.png?raw=true)

Steps for segmentation of the cropped images:
* **A.** Open the cropped image for segmentation and select "Plugins" >> "Segmentation" >> "Trainable Weka Segmentation".
* **B.** A Trainable Weka Segmentation dialog box will appear; select "Load classifier" (Callose quantification.model).
* **C.** Select "Callose segmentation.model" file. A dialog box will appear indicating successful loading of the classifier.
* **D.** Select "Apply classifier" option.
* **E.** Select the file to be segmented i.e., the images that were cropped. A dialog box of probability maps will appear; select "No" option.
* **F.** The resulting image is segmented and save this image in .tiff format in "Segmented images" folder.

---

### Step 4: Enumerate Callose Depositions
![Step 4: Enumerate callose](https://github.com/iitj-mpg-lab/callose-quantification-imagej/blob/main/example_data/image4.png?raw=true)

Steps to enumerate the callose depositions:
* **A.** Open Segmented images in ImageJ software.
* **B.** On the menu bar, select "Plugins" >> "Macros" >> "Run" (`Clear Measure Resize.ijm`).
* **C.** Select "Callose analyse particles" option.
* **D.** The resulting image shows the number of callose depositions detected.
* **Summary:** A summary dialog box will appear showing the number of callose depositions in the image analysed.

### Please refer the article titled "An optimized protocol to detect callose deposition in soybean lateral roots during fungal infections" for detailed step by step usage instructions. 


