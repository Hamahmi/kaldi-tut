# Kaldi tutorial

The digits recordings data has been taken from [here](https://github.com/Jakobovski/free-spoken-digit-dataset/tree/master/recordings).

### Initial Steps to use Kaldi
##### Please note that it's better if you used Linux, for me I'm using Ubuntu on Windows (WSL)
1. Download Kaldi using  
`
git clone https://github.com/kaldi-asr/kaldi.git kaldi-trunk --origin golden
`
2. Go to `kaldi-trunk/tools/extra/` and run the script `./check_dependencies.sh`, follow the instructions and re-run it again till it outputs :  
```
./check_dependencies.sh: all OK.  
```
3. Install Kaldi using by doing the following: 
    In `kaldi-trunk/tools/` do : 
    ```
    make -j 8; cd ../src; ./configure; make -j 8
    ```
    _-j 8 will run 8 jobs in parallel because it may take a while, you can change it to the number of processors you have. use ``` nproc ``` to check how many logical processors your device have_
4. Go to `kaldi-trunk/tools/` and install SRILM using the script `./install_srilm.sh` **Note that you may need to go to [SRILM website](http://www.speech.sri.com/projects/srilm/download.html) and download the SRILM and put it in the directory `kaldi-trunk/tools/` and rename it to `srilm.tgz` before running the script**
5. Go to `kaldi-trunk/egs/` and clone this repo using
`git clone https://github.com/Hamahmi/kaldi-tut.git`
6. Source `tools/env.sh` in `path.sh` by adding 
```
# Sourcing tools/env.sh ~H
. ../../tools/env.sh
```
in `path.sh`

7. Change the paths in the files to be correct **instead of _home/hamahmi/kaldi-trunk/_ use your own path**
8. Run the scripts `script_for_utt2spk.sh`, `script_for_wav.scp.sh`, and `script_for_text.sh` in both `kaldi-trunk/egs/kaldi-tut/digits_audio/test/` and `kaldi-trunk/egs/kaldi-tut/digits_audio/train`to generate the respective files.
Completing these steps ensures that the data has been properly set up.
9. Run the script `./run.sh` :D 

For further steps, kaldi-for-dummies can be followed from [here](http://kaldi-asr.org/doc/kaldi_for_dummies.html).
