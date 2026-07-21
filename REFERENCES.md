# References

Papers cited by the tutorial series, grouped by the notebook they belong to. Each entry says in one or two sentences what the paper gives the reader.

## 01 · Spiking neurons and encoding

Hodgkin, A. L., & Huxley, A. F. (1952). "A quantitative description of membrane current and its application to conduction and excitation in nerve." *Journal of Physiology*.
Shows the full biophysical model that LIF simplifies away, so the reader can see what the tutorial's update rule kept and what it dropped.

Maass, W. (1997). "Networks of spiking neurons: the third generation of neural network models." *Neural Networks*.
The source for the claim that opens the series, that spike timing gives a computational model distinct from rate-based networks.

Izhikevich, E. M. (2003). "Simple model of spiking neurons." *IEEE Transactions on Neural Networks*.
Sits between LIF and Hodgkin-Huxley in cost and realism, and reproduces many cortical firing patterns with two variables, which makes it a good second neuron to implement.

Brette, R., & Gerstner, W. (2005). "Adaptive exponential integrate-and-fire model as an effective description of neuronal activity." *Journal of Neurophysiology*.
Adds spike-triggered adaptation to LIF and connects directly to the `snn.Synaptic` appendix.

Gerstner, W., Kistler, W. M., Naud, R., & Paninski, L. (2014). *Neuronal Dynamics: From Single Neurons to Networks and Models of Cognition*. Cambridge University Press.
The standard textbook for the notation used throughout the series, useful as the reference a reader can follow up in.

Perez-Nieves, N., Leung, V. C. H., Dragotti, P. L., & Goodman, D. F. M. (2021). "Neural heterogeneity promotes robust learning." *Nature Communications*.
Gives a ready experiment for chapter 01: draw the membrane time constant from a distribution instead of fixing it, and measure the gain in robustness.

Lichtsteiner, P., Posch, C., & Delbruck, T. (2008). "A 128x128 120 dB 15 us latency asynchronous temporal contrast vision sensor." *IEEE Journal of Solid-State Circuits*.
The hardware that produces delta-encoded spikes, which grounds the delta encoding section in a real device.

Gallego, G., et al. (2020). "Event-based vision: a survey." *IEEE Transactions on Pattern Analysis and Machine Intelligence*.
Surveys what event cameras measure and how the data is processed, and serves as the entry point for readers who want real event data.

Orchard, G., Jayawant, A., Cohen, G. K., & Thakor, N. (2015). "Converting static image datasets to spiking neuromorphic datasets using saccades." *Frontiers in Neuroscience*.
Introduces N-MNIST, the smallest realistic spiking dataset for readers ready to move past synthetic input.

Amir, A., et al. (2017). "A low power, fully event-based gesture recognition system." *CVPR*.
Source of the DVS128 Gesture dataset, a temporal task where spike timing carries the signal.

Li, H., Liu, H., Ji, X., Li, G., & Shi, L. (2017). "CIFAR10-DVS: an event-stream dataset for object classification." *Frontiers in Neuroscience*.
An event-camera version of a familiar benchmark, which lets readers compare SNN results against ANN numbers they already know.

Cramer, B., Stradmann, Y., Schemmel, J., & Zenke, F. (2020). "The Heidelberg spiking data sets for the systematic evaluation of spiking neural networks." *IEEE Transactions on Neural Networks and Learning Systems*.
Audio datasets built for SNNs, where the task requires integrating information over time.

## 02 · STDP and unsupervised learning

Hebb, D. O. (1949). *The Organization of Behavior*. Wiley.
The original statement of the correlation principle that every rule in the series builds on.

Markram, H., Lübke, J., Frotscher, M., & Sakmann, B. (1997). "Regulation of synaptic efficacy by coincidence of postsynaptic APs and EPSPs." *Science*.
The first experimental demonstration that the order of pre and post spikes decides the sign of the weight change.

Bi, G. Q., & Poo, M. M. (1998). "Synaptic modifications in cultured hippocampal neurons: dependence on spike timing, synaptic strength, and postsynaptic cell type." *Journal of Neuroscience*.
Measures the STDP learning window that the tutorial plots and implements.

Bi, G. Q., & Poo, M. M. (2001). "Synaptic modification by correlated activity: Hebb's postulate revisited." *Annual Review of Neuroscience*.
A review that places the timing window inside the broader Hebbian picture, good for readers who want the biology in more depth.

Song, S., Miller, K. D., & Abbott, L. F. (2000). "Competitive Hebbian learning through spike-timing-dependent synaptic plasticity." *Nature Neuroscience*.
The direct source for the competitive STDP setup in this chapter, where competition plus weight bounds drive neurons toward selective receptive fields.

Oja, E. (1982). "Simplified neuron model as a principal component analyzer." *Journal of Mathematical Biology*.
Turns the weight normalization step into a principled rule with a known fixed point, and explains why the weights converge instead of growing without bound.

Bienenstock, E. L., Cooper, L. N., & Munro, P. W. (1982). "Theory for the development of neuron selectivity: orientation specificity and binocular interaction in visual cortex." *Journal of Neuroscience*.
The BCM sliding threshold, which is the theory behind the adaptive threshold experiment already in this chapter.

Turrigiano, G. G., & Nelson, S. B. (1999). "Homeostatic plasticity in neuronal networks: the more things change, the more they stay the same." *Trends in Neurosciences*.
Explains why a network with Hebbian learning needs a stabilizing mechanism, which motivates the homeostasis section.

Pfister, J. P., & Gerstner, W. (2006). "Triplets of spikes in a model of spike timing-dependent plasticity." *Journal of Neuroscience*.
Shows where the pairwise rule breaks down and how a triplet rule captures firing-rate effects that pair STDP misses.

Clopath, C., Büsing, L., Vasilaki, E., & Gerstner, W. (2010). "Connectivity reflects coding: a model of voltage-based STDP with homeostasis." *Nature Neuroscience*.
Replaces spike timing with postsynaptic voltage as the plasticity variable, which links this chapter to the membrane potential from chapter 01.

Diehl, P. U., & Cook, M. (2015). "Unsupervised learning of digit recognition using spike-timing-dependent plasticity." *Frontiers in Computational Neuroscience*.
The reference implementation for the competitive network in this chapter, including lateral inhibition and adaptive thresholds.

Masquelier, T., Guyonneau, R., & Thorpe, S. J. (2008). "Spike timing dependent plasticity finds the start of repeating patterns in continuous spike trains." *PLoS ONE*.
Demonstrates that STDP alone locks onto a repeating pattern buried in noise, a striking result to reproduce.

Kheradpisheh, S. R., Ganjtabesh, M., Thorpe, S. J., & Masquelier, T. (2018). "STDP-based spiking deep convolutional neural networks for object recognition." *Neural Networks*.
Scales STDP feature learning to several layers, showing how far the unsupervised rule reaches.

Nessler, B., Pfeiffer, M., Buesing, L., & Maass, W. (2013). "Bayesian computation emerges in generic cortical microcircuits through spike-timing-dependent plasticity." *PLoS Computational Biology*.
Reads STDP with winner-take-all as expectation maximization, which gives the chapter a probabilistic interpretation.

Olshausen, B. A., & Field, D. J. (1996). "Emergence of simple-cell receptive field properties by learning a sparse code for natural images." *Nature*.
The classic result on learned receptive fields, worth putting beside the STDP receptive fields so readers can compare what the two objectives produce.

## 03 · Three-factor learning and R-STDP

Izhikevich, E. M. (2007). "Solving the distal reward problem through linkage of STDP and dopamine signaling." *Cerebral Cortex*.
The origin of the eligibility trace as a solution to delayed reward, which is exactly the mechanism this chapter implements.

Florian, R. V. (2007). "Reinforcement learning through modulation of spike-timing-dependent synaptic plasticity." *Neural Computation*.
Derives reward-modulated STDP from a reinforcement learning objective, and gives the eligibility trace form that lets the rule survive a delayed reward.

Legenstein, R., Pecevski, D., & Maass, W. (2008). "A learning theory for reward-modulated spike-timing-dependent plasticity with application to biofeedback." *PLoS Computational Biology*.
States the conditions under which reward-modulated STDP converges, which explains why the baseline subtraction in the reward term matters.

Frémaux, N., & Gerstner, W. (2016). "Neuromodulated spike-timing-dependent plasticity, and theory of three-factor learning rules." *Frontiers in Neural Circuits*.
The reference statement of the three-factor form used in this chapter, including the role of the baseline subtraction in the reward term.

Gerstner, W., Lehmann, M., Liakoni, V., Corneil, D., & Brea, J. (2018). "Eligibility traces and plasticity on behavioral time scales: experimental support of neoHebbian three-factor learning rules." *Frontiers in Neural Circuits*.
Collects the experimental evidence that eligibility traces exist in real synapses on the timescale the chapter assumes.

Mazurek, S., Caputa, J., Argasiński, J. K., & Wielgosz, M. (2025). "Three-factor learning in spiking neural networks: an overview of methods and trends from a machine learning perspective." arXiv:2504.05341.
A recent map of the three-factor field, useful for showing readers where this chapter sits among current methods.

## 04 · Gradient-based learning

Bohte, S. M., Kok, J. N., & La Poutré, H. (2002). "Error-backpropagation in temporally encoded networks of spiking neurons." *Neurocomputing*.
The first backpropagation rule for spiking networks, which gives historical context for the surrogate gradient that replaced it.

Gütig, R., & Sompolinsky, H. (2006). "The tempotron: a neuron that learns spike timing-based decisions." *Nature Neuroscience*.
A supervised rule for a single spiking neuron, small enough to implement and useful for showing what one neuron can classify.

Lee, J. H., Delbruck, T., & Pfeiffer, M. (2016). "Training deep spiking neural networks using backpropagation." *Frontiers in Neuroscience*.
An early demonstration that treating the membrane potential as the differentiable signal makes deep SNN training work.

Wu, Y., Deng, L., Li, G., Zhu, J., & Shi, L. (2018). "Spatio-temporal backpropagation for training high-performance spiking neural networks." *Frontiers in Neuroscience*.
Defines the standard way to backpropagate through both layers and time steps, which is the method the chapter's BPTT section uses.

Shrestha, S. B., & Orchard, G. (2018). "SLAYER: spike layer error reassignment in time." *NeurIPS*.
Handles credit assignment across synaptic delays, and remains a common baseline in later work.

Zenke, F., & Ganguli, S. (2018). "SuperSpike: supervised learning in multilayer spiking neural networks." *Neural Computation*.
Derives a three-factor learning rule from a surrogate gradient, which ties chapter 04 back to chapter 03.

Neftci, E. O., Mostafa, H., & Zenke, F. (2019). "Surrogate gradient learning in spiking neural networks." *IEEE Signal Processing Magazine*.
The source for the surrogate gradient method this chapter is built on, including the common choices of surrogate function.

Wu, Y., Deng, L., Li, G., Zhu, J., Xie, Y., & Shi, L. (2019). "Direct training for spiking neural networks: faster, larger, better." *AAAI*.
Adds normalization and encoding fixes that make direct training stable at larger scale.

Bellec, G., Salaj, D., Subramoney, A., Legenstein, R., & Maass, W. (2018). "Long short-term memory and learning-to-learn in networks of spiking neurons." *NeurIPS*.
Introduces the adaptive threshold neuron that gives spiking networks long working memory, and sets up the e-prop paper that follows.

Bellec, G., Scherr, F., Subramoney, A., Hajek, E., Salaj, D., Legenstein, R., & Maass, W. (2020). "A solution to the learning dilemma for recurrent networks of spiking neurons." *Nature Communications*.
The e-prop rule implemented in this chapter, which factors the BPTT gradient into a local eligibility trace and a learning signal.

Lillicrap, T. P., Cownden, D., Tweed, D. B., & Akerman, C. J. (2016). "Random synaptic feedback weights support error backpropagation for deep learning." *Nature Communications*.
Feedback alignment, which removes the weight transport requirement and is the demo in section 6.

Nøkland, A. (2016). "Direct feedback alignment provides learning in deep neural networks." *NeurIPS*.
Sends the error straight from the output to each layer, taking the feedback alignment idea one step further.

Kaiser, J., Mostafa, H., & Neftci, E. (2020). "Synaptic plasticity dynamics for deep continuous local learning (DECOLLE)." *Frontiers in Neuroscience*.
Gives each layer its own local loss through a fixed random readout, which is the spatially local rule in section 7.

Zenke, F., & Vogels, T. P. (2021). "The remarkable robustness of surrogate gradient learning for instilling complex function in spiking neural networks." *Neural Computation*.
Measures how much the choice of surrogate function matters, which answers a question readers ask as soon as they see the surrogate.

Wunderlich, T. C., & Pehle, C. (2021). "Event-based backpropagation can compute exact gradients for spiking neural networks." *Scientific Reports*.
Computes exact gradients through spike times, which shows what the surrogate approximates and what it costs in accuracy.

Xiao, M., Meng, Q., Zhang, Z., He, D., & Lin, Z. (2022). "Online training through time for spiking neural networks." *NeurIPS*.
Trains forward in time with memory that stays constant as the sequence grows, and the resulting update takes the three-factor Hebbian form, which makes it the natural step after e-prop.

Eshraghian, J. K., et al. (2023). "Training spiking neural networks using lessons from deep learning." *Proceedings of the IEEE*.
The paper behind snnTorch, so it documents the library the series runs on and the design choices in its neuron classes.

## 05 · Learning a task with local rules

Maass, W., Natschläger, T., & Markram, H. (2002). "Real-time computing without stable states: a new framework for neural computation based on perturbations." *Neural Computation*.
The liquid state machine, which is the design behind a fixed random hidden layer feeding a trained local readout.

Wunderlich, T. C., Kungl, A. F., Müller, E., Schemmel, J., & Petrovici, M. (2019). "Brain-inspired hardware for artificial intelligence: accelerated learning in a physical-model spiking neural network." *ICANN 2019*, LNCS 11727.
Trains a spiking network to play a simplified Pong with reward-modulated STDP on neuromorphic hardware, which is the closest published precedent for this chapter.

Tang, G., Kumar, N., & Michmizos, K. P. (2020). "Reinforcement co-learning of deep and spiking neural networks for energy-efficient mapless navigation with neuromorphic hardware."
A robotics task where a spiking policy runs on neuromorphic hardware, useful for showing what the approach is good for.

Tang, G., Kumar, N., Yoo, R., & Michmizos, K. P. (2020). "Deep reinforcement learning with population-coded spiking neural network for continuous control."
Population coding for continuous actions, which extends the discrete action setup used in chapter 03.

Tan, W., Patel, D., & Kozma, R. (2021). "Strategy and benchmark for converting deep Q-networks to event-driven spiking neural networks." *AAAI*.
Sets a benchmark for spiking agents on Atari, which gives a reference point for how far local rules get on the same tasks.

## 06 · Predictive coding and energy-based local learning

Rao, R. P. N., & Ballard, D. H. (1999). "Predictive coding in the visual cortex: a functional interpretation of some extra-classical receptive-field effects." *Nature Neuroscience*.
The founding predictive coding model, and the source of the value node and error node structure used in this chapter.

Whittington, J. C. R., & Bogacz, R. (2017). "An approximation of the error backpropagation algorithm in a predictive coding network with local Hebbian synaptic plasticity." *Neural Computation*.
Proves that predictive coding converges to the backpropagation gradient under stated conditions, which is the central claim the chapter demonstrates.

Millidge, B., Seth, A., & Buckley, C. L. (2021). "Predictive coding: a theoretical and experimental review." arXiv:2107.12979.
A current review that separates the theory from the biological evidence, useful as further reading.

Scellier, B., & Bengio, Y. (2017). "Equilibrium propagation: bridging the gap between energy-based models and backpropagation." *Frontiers in Computational Neuroscience*.
Defines equilibrium propagation, where the same dynamics handle inference and learning and the weight update reads off two settled states.

Hinton, G. (2022). "The forward-forward algorithm: some preliminary investigations." arXiv:2212.13345.
Replaces the backward pass with a second forward pass on negative data, giving the chapter a local rule with a goodness objective instead of an energy function.

Guerguiev, J., Lillicrap, T. P., & Richards, B. A. (2017). "Towards deep learning with segregated dendrites." *eLife*.
Uses separate dendritic compartments to carry feedforward and feedback signals in one neuron, which is a concrete answer to where the error signal lives.

Sacramento, J., Ponte Costa, R., Bengio, Y., & Senn, W. (2018). "Dendritic cortical microcircuits approximate the backpropagation algorithm." *NeurIPS*.
Builds a microcircuit whose steady state encodes the backpropagation error, extending the dendritic idea into a full network.

Payeur, A., Guerguiev, J., Zenke, F., Richards, B. A., & Naud, R. (2021). "Burst-dependent synaptic plasticity can coordinate learning in hierarchical circuits." *Nature Neuroscience*.
Uses burst rate as a second channel so one connection carries both activity and error, which is a recent and testable answer to credit assignment.

Lillicrap, T. P., Santoro, A., Marris, L., Akerman, C. J., & Hinton, G. (2020). "Backpropagation and the brain." *Nature Reviews Neuroscience*.
Reviews what the brain would need in order to do something like backpropagation, and works well as the closing reference for the series.

## Proposed chapter: ANN to SNN conversion

Diehl, P. U., Neil, D., Binas, J., Cook, M., Liu, S. C., & Pfeiffer, M. (2015). "Fast-classifying, high-accuracy spiking deep networks through weight and threshold balancing." *IJCNN*.
Introduces weight and threshold balancing, the first practical recipe for turning a trained ANN into a working SNN.

Rueckauer, B., Lungu, I. A., Hu, Y., Pfeiffer, M., & Liu, S. C. (2017). "Conversion of continuous-valued deep networks to efficient event-driven networks for image classification." *Frontiers in Neuroscience*.
The standard conversion reference, covering how to handle max pooling, batch norm, and softmax in spiking form.

Sengupta, A., Ye, Y., Wang, R., Liu, C., & Roy, K. (2019). "Going deeper in spiking neural networks: VGG and residual architectures." *Frontiers in Neuroscience*.
Scales conversion to deep architectures with a threshold balancing scheme that works layer by layer.

Deng, S., & Gu, S. (2021). "Optimal conversion of conventional artificial neural networks to spiking neural networks." *ICLR*.
Analyzes conversion error directly and reduces the number of time steps needed for accurate inference.

Bu, T., Fang, W., Ding, J., Dai, P., Yu, Z., & Huang, T. (2023). "Optimal ANN-SNN conversion for high-accuracy and ultra-low-latency spiking neural networks." *ICLR*.
Uses a quantized activation during ANN training so that the converted network works at very few time steps.

## Proposed chapter: deep SNN architectures

Fang, W., Yu, Z., Chen, Y., Masquelier, T., Huang, T., & Tian, Y. (2021). "Incorporating learnable membrane time constant to enhance learning of spiking neural networks." *ICCV*.
Makes the membrane time constant a trained parameter, which turns a constant fixed in chapter 01 into something the network chooses.

Zheng, H., Wu, Y., Deng, L., Hu, Y., & Li, G. (2021). "Going deeper with directly-trained larger spiking neural networks." *AAAI*.
Introduces threshold-dependent batch normalization, which is what makes deep SNNs trainable from scratch.

Fang, W., Yu, Z., Chen, Y., Huang, T., Masquelier, T., & Tian, Y. (2021). "Deep residual learning in spiking neural networks." *NeurIPS*.
Fixes the way residual connections interact with spikes so that identity mapping still holds in a spiking network.

Zhou, Z., Zhu, Y., He, C., Wang, Y., Yan, S., Tian, Y., & Yuan, L. (2022). "Spikformer: when spiking neural network meets transformer." *ICLR*.
The first spiking self-attention that works at scale, replacing softmax attention with spike-based operations.

Yao, M., Hu, J., Zhou, Z., Yuan, L., Tian, Y., Xu, B., & Li, G. (2023). "Spike-driven transformer." *NeurIPS*.
Keeps every operation in the transformer event-driven, so the energy argument in the series holds for the whole model.

Yao, M., Zhao, G., Zhang, H., Hu, Y., Deng, L., Tian, Y., Xu, B., & Li, G. (2023). "Attention spiking neural networks." *IEEE Transactions on Pattern Analysis and Machine Intelligence*.
Adds attention over the temporal dimension, which is a mechanism specific to networks that process spikes over time.

Zhu, R. J., Zhao, Q., Li, G., & Eshraghian, J. K. (2023). "SpikeGPT: generative pre-trained language model with spiking neural networks." arXiv:2302.13939.
The first language model built from spiking units, and a useful marker of what the approach can reach.

Hammouamri, I., Khalfaoui-Hassani, I., & Masquelier, T. (2023). "Learning delays in spiking neural networks using dilated convolutions with learnable spacings." *ICLR*.
Treats axonal delay as a trained parameter, which adds a second timing variable alongside the weight.

Fang, W., et al. (2023). "SpikingJelly: an open-source machine learning infrastructure platform for spike-based intelligence." *Science Advances*.
A framework with CUDA kernels for spiking layers, worth naming for readers who outgrow the CPU-scale code in the series.

Pan, Y., et al. (2025). "SpikingBrain: spiking brain-inspired large models." arXiv:2509.05276.
Trains spiking models at 7B and 76B scale with linear attention, which shows the current ceiling for the approach.

## Proposed chapter: hardware and energy

Merolla, P. A., et al. (2014). "A million spiking-neuron integrated circuit with a scalable communication network and interface." *Science*.
TrueNorth, the first large neuromorphic chip, and the source of the power figures that back the energy argument.

Furber, S. B., Galluppi, F., Temple, S., & Plana, L. A. (2014). "The SpiNNaker project." *Proceedings of the IEEE*.
A many-core system built for spike communication, showing a different hardware answer to the same problem.

Davies, M., et al. (2018). "Loihi: a neuromorphic manycore processor with on-chip learning." *IEEE Micro*.
Supports local plasticity rules in silicon, which is where the learning rules from chapters 02 and 03 actually run.

Pei, J., et al. (2019). "Towards artificial general intelligence with hybrid Tianjic chip architecture." *Nature*.
Runs spiking and non-spiking networks on one chip, and demonstrates the result on a self-balancing bicycle.

Davies, M., et al. (2021). "Advancing neuromorphic computing with Loihi: a survey of results and outlook." *Proceedings of the IEEE*.
Collects measured energy and latency numbers across tasks, which is the data needed to state the efficiency claim carefully.

Schuman, C. D., Kulkarni, S. R., Parsa, M., Mitchell, J. P., Date, P., & Kay, B. (2022). "Opportunities for neuromorphic computing algorithms and applications." *Nature Computational Science*.
Maps which problems suit neuromorphic hardware, which helps a reader decide when to reach for an SNN.

Deng, L., Wu, Y., Hu, X., Liang, L., Ding, Y., Li, G., Zhao, G., Li, P., & Xie, Y. (2019). "Rethinking the performance comparison between SNNs and ANNs." *Neural Networks*.
Examines the efficiency claim under matched conditions and reports where the advantage holds, which keeps the opening argument of the series honest.

## Surveys

Tavanaei, A., Ghodrati, M., Kheradpisheh, S. R., Masquelier, T., & Maida, A. (2019). "Deep learning in spiking neural networks." *Neural Networks*.
A broad survey of SNN training methods, good as a single starting reference for readers.

Taherkhani, A., Belatreche, A., Li, Y., Cosma, G., Maguire, L. P., & McGinnity, T. M. (2020). "A review of learning in biologically plausible spiking neural networks." *Neural Networks*.
Focuses on local and biologically motivated rules, which is the exact scope of this series.

Caviglia, A., Marostica, F., Bardini, R., Savino, A., & Di Carlo, S. (2026). "NeuroTrain: surveying local learning rules for spiking neural networks with an open benchmarking framework." arXiv:2605.15058.
Gives a taxonomy and a benchmark for local learning rules, so readers can locate STDP, R-STDP, e-prop, and DECOLLE on a shared map.
