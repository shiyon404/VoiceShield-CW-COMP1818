# VoiceShield AI

VoiceShield uses AASIST to distinguish genuine speech from synthetic or voice-converted speech. The experiment tests how bandwidth limitation affects detection and whether fine-tuning with filtered audio improves performance.

## Downloads and source code

- [Complete submission folder on Google Drive](https://drive.google.com/drive/folders/1hwie90TA5Fg8U6blHkxccMpOSL9FdNFX?usp=drive_link)
- [Project source on GitHub](https://github.com/shiyon404/VoiceShield-CW-COMP1818)

## Files

- `CODE_VoiceShield.ipynb` contains the setup, saved-model demonstration, results checks and optional experiment reproduction code.
- `VoiceShield.zip` contains the saved checkpoints, experiment settings, training IDs, logs and result CSVs.
- `LA_zenodo.zip` contains the ASVspoof 2019 Logical Access dataset.
- `requirements.txt` lists the dependencies for local execution.

## Run the saved model in Colab

1. Download `CODE_VoiceShield.ipynb` from the shared Drive folder and open it in Google Colab. A T4 GPU is recommended.
2. Run **Section 1.1** to set up the environment.
3. Run **Section 1.2** to prepare the files. The notebook reuses files already extracted in the runtime and downloads any missing ZIPs directly from the shared Drive folder. It checks the dataset ZIP checksum before extraction.
4. Run **Sections 1.3 and 1.4** to verify the saved checkpoint and test it on two development recordings. This demonstration requires no training.
5. Run the saved-results cells in **Section 2** to inspect the experiment evidence. Leave `RUN_EXPERIMENTS = False` for the demonstration and results checks.

If the automatic download fails, download `VoiceShield.zip` and `LA_zenodo.zip` from Drive, upload both to `/content` using Colab’s Files panel, and rerun Section 1.2. Keep the original filenames.

## Run locally in VS Code

Install the dependencies in `requirements.txt` and make sure Git is available. Open the notebook in VS Code, select your Python environment and place both ZIPs in the project folder shown by Section 1.1. Then run Section 1 in order.

## Interpreting the results

The two demonstration recordings check that the saved model loads and produces scores. The reported metrics come from the completed Colab experiment. The interrupted laptop run is separate.

The experiment uses a 300–3400 Hz band-pass filter at a 16 kHz sampling rate. It tests bandwidth limitation. A full telephone connection would introduce other effects, such as codec compression and packet loss.

## Sources

- [Official AASIST implementation, pretrained weights and MIT licence](https://github.com/clovaai/aasist)
- [ASVspoof 2019 dataset on Zenodo](https://zenodo.org/records/6906306)
