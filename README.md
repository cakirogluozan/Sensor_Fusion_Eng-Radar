## Sensor Fusion Nanodegree
### Radar Target Generation and Detection 


- FMCW Waveform Design Criteria 1: "For given system requirements the calculated slope should be around 2e13" 

        Estimated slope = 2.0455e+13

- Simulation Loop Criteria 1: "A beat signal should be generated such that once range FFT implemented, it gives the correct range i.e the initial position of target assigned with an error margin of +/- 10 meters."

        Given R = 100, estimated R = 97.

- Range FFT (1st FFT) Criteria 1: "A correct implementation should generate a peak at the correct range, i.e the
initial position of target assigned with an error margin of +/- 10 meters."

        Given R = 100, estimated R = 97.

- 2D CFAR Criteria 1: "The 2D CFAR processing should be able to suppress the noise and separate the target signal. The output should match the image shared in walkthrough."
  
        The result can be visualized by running the code.
    
- 2D CFAR Criteria 2:   "In a README file, write brief explanations for the following:"

    - Implementation steps for the 2D CFAR process.

      * *Definition of Radar Specs*
      * *FMCW Waveform Generation*
        * *B, Tchirp and slope values Calculation*
        * *Nd and Nr initialization by 128 and 1024, respectively*
      * *Signal generation and Moving Target Simulation*
        * *Transmit and receive signal*
        * *Beat Signal evaluation and visualization*
      * *Range measurement*
        * *1D FFT evaluation of Beat Signal and visualization*
      * *2D FFT evaluation, dB normalization and visualization*
      * *CFAR Implementation*
        * *Initializing parameters: R_train, R_guard, D_train, D_guard, offset and noise level*
        * *Evaluation of RDM*
    - Selection of Training, Guard cells and offset.

        * *Too low and too high values cause False Positive or False Negative. Selection of Training cell parameters (both in Range and Doppler dimension) as 50 worked well in my project.*
        * *Change Guard cell value in Range dimension does not have a big effect on the performance yet it has a big impact in Doppler dimension.*
        * *I observed the peak value and ground values about 42 and 25 respectively. I selected 18 as I eliminate all the noises and lower posibilities.*

    - Steps taken to suppress the non-thresholded cells at the edges.
      - *While RDM has value either 0 or 1 by thresholding, the values between 0 and 1 is suppressed to 0.* 
