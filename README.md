# pyNEUNET

## Version number
current version = '0.1.0'

## Installation
In the terminal, go to whatever directory you want the module to be available in and type

    pip install git+https://github.com/sfayfar/pyNEUNET-Detector.git

## Import
To import the entire module, write

    import pyNEUNET

at the top of your Python file. To import only the detectors.py file (for reading data), write

    from pyNEUNET import detectors

## Usage
Create new reader object:

    reader = detectors.Linear3HePSD()

Set exposure time (seconds) and number of position bins (default of 350 bins ~ 1 mm resolution):

    reader.exposure_time = 30

    reader.bins = 500

Run a sanity check to make sure functions run as they should:

    reader.sanity_check()

Read data:

    output = reader.read()

If you want to save, graph, overwrite old files, name files, and choose folder to save to:

    output = reader.read(save=True, graph=True, overwrite=True, test_label="name_of_file", fldr="name_of_folder")

If you want to print messages during a reading:

    output = reader.read(verbose=True)

If you want to change output format to a tuple containing start time, elapsed time, histograms:

    output = reader.read(output_format=None)

Once you're done reading, shut down the NEUNET register:

    reader.unstage()