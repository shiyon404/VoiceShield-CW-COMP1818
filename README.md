# VoiceShield AI

Detecting genuine and synthetic or voice-converted speech with AASIST, with a controlled bandwidth-adaptation experiment.

## Downloads and source code

- [Complete submission folder on Google Drive](https://drive.google.com/drive/folders/1hwie90TA5Fg8U6blHkxccMpOSL9FdNFX?usp=drive_link): notebook, dependencies, dataset archive, saved checkpoints and experiment results.
- [Project source on GitHub](https://github.com/shiyon404/VoiceShield-CW-COMP1818).

## Files

- `CODE_VoiceShield.ipynb`: setup instructions, saved-model demonstration, recorded experiment evidence and optional reproduction code.
- `VoiceShield.zip`: saved model checkpoints, experiment settings, training IDs, logs and result CSV files.
- `LA_zenodo.zip`: ASVspoof 2019 Logical Access dataset archive.
- `requirements.txt`: dependencies for local execution. Colab already supplies PyTorch and NumPy; follow the notebook setup instructions.

## Run the saved model in Colab

1. Download the notebook and both ZIP files from the Google Drive folder linked above.
2. Open `CODE_VoiceShield.ipynb` in Google Colab and select a T4 GPU runtime.
3. Upload `VoiceShield.zip` and `LA_zenodo.zip` to the Colab Files panel under `/content`. Keep these ZIP filenames unchanged.
4. Run Section 1 in order. It locates/extracts the files, checks the checkpoint hash and tests two development recordings. No training is needed.
5. Run the saved-evidence cells in Section 2 to read the completed metrics and training logs. Leave `RUN_EXPERIMENTS=False` unless deliberately reproducing the full experiment.

Two demonstration recordings are not an accuracy estimate. The main results are from the completed Colab experiment, the interrupted laptop repeat is separate. The filter limits bandwidth to 300–3400 Hz while retaining 16 kHz sampling. It does not simulate a complete telephone connection.


## Sources and assistance
Official AASIST code, pretrained model and MIT licence: https://github.com/clovaai/aasist 

Dataset source: https://zenodo.org/records/6906306.

