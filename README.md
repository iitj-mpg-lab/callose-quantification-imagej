# callose-quantification-imagej
Automated ImageJ-based workflow for callose quantification using machine learning segmentation and particle analysis.
The scripts and trained model provided in this repository are associated with the protocol described in the article *“An optimized protocol to detect callose deposition in soybean lateral roots during fungal infections.”*
## 🔍 Use case
- Measures root area from microscopy images  
- Identifies callose deposits using a trained Weka classifier  
- Automatically counts callose particles  
 
## 📁 Repository structure
- `macros/` – ImageJ macro scripts (`.ijm`)  
- `model/` – Pre-trained classifier for callose detection  
- `example_data/` – Sample images and outputs  

## ▶️ Quick start
1. Open your image in ImageJ and set the scale  
2. Run `Clear Measure Resize.ijm` to crop and measure root area  
3. Load and apply the classifier (`Callose quantification.model`)  
4. Run `Callose analyse particles.ijm` to count callose deposits
### Please refer the article titled "An optimized protocol to detect callose deposition in soybean lateral roots during fungal infections" for detailed step by step usage instructions. 


