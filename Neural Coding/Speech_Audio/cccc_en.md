# Traditional Audio Codecs
Signal processing based approach: **Opus, EVS**  
Related technologies: **LPC, CELP, MDCT ...**  
>*produce high coding efficiency for general audio while supporting various bitrates, sampling rates, and  real-time compression.*
# Post-proceesing after existing codecs
[Bandwidth Extension: SEANet](./REAL_TIME_SPEECH_FREQUENCY_BANDWIDTH_EXTENSION.pdf)  
[Audio Denoising: SEGAN](./AUDIO_CODEC_ENHANCEMENT_WITH_GENERATIVE_ADVERSARIAL_NETWORKS.pdf)  
[PLC: WaveNetEQ](./WaveNetEQ_Packet_Loss_Concealment_with_WaveRNN.pdf)  
...
# Neural Based Audio Codecs
## Neural speech synthesis / generative models based:
+ **[LPCNet](./A_Real_Time_Wideband_Neural_Vocoder_at_1.6_kbps_Using_LPCNet.pdf): Quantizing the features and using them for speech synthesis to achieve low-bitrate speech coding**
  > hand-crafted features and uniform quantizer
+ **[Opus + Neural Vocoder](./Improving_Opus_Low_Bit_Rate_Quality_with_Neural_Speech_Synthesis.pdf): Resynthesizing speech from the Opus decoded parameters**
  > Obtaining frequency domain features from Opus encoder and performing speech synthesis with LPCNet/WaveNet
+ **[Parametric/Waveform WaveNet Coder](./WAVENET_BASED_LOW_RATE_SPEECH_CODING.pdf): Using WaveNet as a generic genarative model for speech coding**
  > Implicit BWE, parametric coder with the decoded features from Codec2 bitstream, ~~waveform coder~~
+ **[SampleRNN for speech coding](./HIGH_QUALITY_SPEECH_CODING_WITH_SAMPLE_RNN.pdf): Speech coding scheme employing a generative model based on SampleRNN**
  > Higher reconstruction quality can be achieved by allowing a higher bitrate, feature from LPC analysis
+ **[VQ-VAE + WaveNet](./Low_Bit_rate_Speech_Coding_with_VQ_VAE_and_a_WaveNet_Decoder.pdf): A WaveNet based model on discrete units obtained from a VQ-VAE**
  > Adjusting the origin VQVAE (audio) architecture to make it speaker and prosody transparent for speech coding, end-to-end learned
+ **[HVQVAE + WaveRNN/Parametric Vocoder](./Architecture_for_Variable_Bitrate_Neural_Speech_Codec_with_Configurable_Computation_Complexity.pdf): Using a HVQVAE for encoding and decoding spectral features at different bitrates and feeding them to WaveRNN/Parametric vocoders**
  > Variable bitrates, packet losses, two-stage training strategy
+ **[Lyra](./GENERATIVE_SPEECH_CODING_WITH_PREDICTIVE_VARIANCE_REGULARIZATION.pdf): 3 kb/s for real-world speech signals at reasonable computational complexity**
  > Quantifying log mel spectrograms and generating waveforms using WaveRNN
## End-to-end neural audio/speech codec
_With Autoencoder + VQ_
+ **[SoundStream(Lyra v2)](./SoundStream_An_End_to_End_Neural_Audio_Codec.pdf): A novel audio codec that can compress speech, music and general audio more efficiently than previous codecs**
  > RVQ for bitrate scalability, STFT-based GAN for further improvement of perception quality, time-domain
+ **[TFNet](./End_to_End_Neural_Speech_Coding_for_Real_Time_Communications.pdf): Consist of 2D causal conv and temporal filter module, for real-time communications**
  > PLC, speech enhancement, TF-domain
+ **[TFNet + CSVQ](./Cross_Scale_Vector_Quantization_for_Scalable_Neural_Speech_Coding.pdf): Cross Scale Vector Quantization is proposed to achieve bitrate scalability**
  > Comparing CSVQ with RVQ  
  ---
  > TFNet and CSVQ version all better than Lyra
+ **[Encodec](./High_Fidelity_Neural_Audio_Compression.pdf): A state-of-the-art real-time, high-fidelity, audio codec leveraging neural networks**
  > RVQ, multi-scale STFT-based GAN, time-domain, loss balancer, lightweight transformer for further compression

_Soft-to-hard scalar quantization_
+ **[]**