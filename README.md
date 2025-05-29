# Tech Pack Assistant for Fashion Designers

In the fashion industry, a Tech Pack serves as a crucial blueprint that communicates design specifications to manufacturers, detailing everything from materials and measurements to construction techniques. Creating a Tech Pack is a meticulous and time-consuming process that requires precision to avoid costly production errors and miscommunications. However, traditional methods often involve repetitive manual tasks, making the process inefficient and prone to human error. 

This is the problem we are attempting to solve in this project - To automate the manual process of tech pack curation, with the aim of drastically reducing the time and mental burden required for this task. We aim to tackle this problem by building an AI assistant which works alongside the designer to execute the tedious parts of the task. The process usually begins with a set of illustration of the design to be manufactured, accompanied with a set of reference images which serves as inspiration for the final product. Given these inputs, our AI will output information such as the materials needed for manufacturing and highlight areas of potential ambiguity in the design. The aim of the final product is to extrapolate these current capabilities to include automatic completion of a tech pack template, and additional information extraction through an interactive conversation interface between the designer and the AI.

## Installation Guide
Installation comprises of the following steps:
* Clone this repository.
* Create the backend environment.
* Install keypoint detection model.
* Install Latex Compiler.
  
### Clone the repository
```
git clone https://github.com/Mudhdhoo/CS224G_TechPackAI.git
```
### Create the environment for the backend
```
conda env create -f backend/environment.yml
```

### Activate the environment
```
conda activate cs224G_techpack_ai
```
### Run the frontend and backend servers
To run it, we need to initialize the backend and frontend servers separately.

#### Activate Backend
```
# Navigate to source directory
cd backend/src
```
```
# Run Backend
python App.py
```

#### Activate Frontend
```
# Navigate to frontend
cd frontend
```
```
# Install all frontend packages
npm install
```
```
# Run frontend
npm run dev
```

### Download Keypoint Detection Model
We use a fine-tuned [ViTPose](https://arxiv.org/abs/2204.12484) model to detect keypoints on clothes. We fine-tuned the model on the [Deep Fashion](https://mmlab.ie.cuhk.edu.hk/projects/DeepFashion.html) dataset. Download the model [here](https://drive.google.com/drive/folders/1mJlOkhoSKFrPDZHlxY2iMQ7UqbmJyT8L?usp=sharing), and place it in the /backend/src/detector directory.

### Install Latex Compiler
This application compiles latex code in the backend to create the tech pack. To enable this, a compiler is needed.
#### Option 1 - MacTex
For Mac, MacTex is an all-in-one software suite that can includes everything for compiling latex code. It can be install [here](https://www.tug.org/mactex/).

#### Option 2 - BasicTex
MacTex is a huge package, occupying around 10 GB. A more space efficient alternative is BasicTex. Install it [here](https://www.tug.org/mactex/morepackages.html), then run the following commands in the terminal:
```
# Export TeX path to make the commands immediately accesible via terminal
export PATH=$PATH:/Library/TeX/texbin
```
```
# Install necessary packages
sudo tlmgr install pagecolor
sudo tlmgr install multirow
sudo tlmgr install lastpage
sudo tlmgr install tgheros
sudo tlmgr tex-gyre
sudo tlmgr makecell
sudo tlmgr enumitem
sudo tlmgr fontawesome5
```

## Running The Application
Create an account and login to begin creating a tech pack. Create a project by uploading the illustrations and reference images. Creation of each tech pack takes around 5-10 minutes.