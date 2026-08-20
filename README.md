***
## KWS (keyword spotting) and applying for EFR32FG24 Silicon lab kit
***
- peiman edalatjoo - winter 2025 - HKA
- Any correction, enhancement, or guidance reported to peiman.edalatjoo@proton.me or edpe1011@h-ka.de will be greatly appreciated.
- To run this code error-free, please read this file first.
- Also there is Useful-Notes file that I suggest you to read when you get some progress.
- The code developed in 7 versions KWS1-7.
***
Description:
An audio dataset of spoken words designed to help train and evaluate keyword spotting systems. Its primary goal is to provide a way to build and test small models that detect when a single word is spoken, from a set of ten target words, with as few false positives as possible from background noise or unrelated speech. Note that in the train and validation set, the label "unknown" is much more prevalent than the labels of the target words or background noise. One difference from the release version is the handling of silent segments. While in the test set the silence segments are regular 1 second files, in the training they are provided as long segments under "background_noise" folder. Here we split these background noise into 1 second clips, and also keep one of the files for the validation set. https://www.tensorflow.org/datasets/catalog/speech_commands
Use Template in VS Code (per environment) with Annaconda:
***
🔹 1: Install Anaconda then Open "Anaconda Prompt or Terminal" and follow below instructions

### 🔹 Creating a new env - important: during below steps consider the sequence!

conda -V (check the installation of conda)

    conda 25.1.1

conda create -n kws-env python=3.10 

    creat an enviroment with a name e.g kws-env for our project 

conda env list

    it gives you a list of enviromantal lists you have had or already created

conda activate your-env-name e.g:  conda activate kws-env

    your prompt tag icon should be change to kws-env 

conda install pandas numpy matplotlib jupyter scikit-learn seaborn

conda install -c conda-forge ffmpeg

🔹 2: Install TensorFlow and typical ML stack

pip install -r pip-requirements.txt 



🔹 3: Register kernel for Jupyter

python -m ipykernel install --user --name kws-env --display-name "kws (TensorFlow, Siliconlab)"
	
🔹 4: continue entering in conda command prompt 

cd /d Your project-path e.g: cd /d D:\ML-Work\Project\KWS

Code 

    it opens VScode

Then:

Press Ctrl+Shift+P → type “Python: Select Interpreter”. or "Notebook: Select Notebook Kernel" and choose -->

kws (TensorFlow, Siliconlab) as a kernel

### Other usefull commands:

Using nbconvert from Terminal to extract py or text(md) from notebook:

If you have Jupyter installed, run this in the terminal

jupyter nbconvert --to script TestPilot3_editing.ipynb

jupyter nbconvert --to markdown your_notebook.ipynb

conda doctor

conda clean --all

conda remove --name your-env-name --all

pip check

pip uninstall tensorflow tensorflow-cpu keras keras-tuner keras-nlp tf-keras tensorflow-text tensorboard ml-dtypes

### saving a conda enviroment:

    conda list --explicit > conda-packages.txt ( this  is bettter than: conda list > conda-list.txt)

    pip freeze > pip-packages.txt

### 🔹 Recreating a new env:

    run annaconda promt as an administrator

    conda deactivate (it deactivates current conda env if it were activated)
    
    conda create --name your-new-env-name --file conda-requirements.txt -c conda-forge

    conda activate your-new-env-name

    install by: pip install -r pip-requirements.txt


    

