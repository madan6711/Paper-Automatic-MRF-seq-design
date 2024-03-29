This repository contains optimized sequence files and results from the following publication: 

Jordan S.P., Hu S.Y., Rozada I., McGivney D.F., Boyacioglu R., Jacob D.C., Huang S., Beverland M., Katzgraber H.G., Troyer M., Griswold M.A., Ma D.. 
Automatic Design of Pulse Sequences for Magnetic Resonance Fingerprinting Using Physics-Inspired Optimizaiton. PNAS,2021, Vol. 118, No. 40. 
(https://www.pnas.org/doi/full/10.1073/pnas.2020516118)

# Automatic-MRF-seq-design

table1.csv:	Unoptimized sequences, c2p480-c2p3000, of different durations, are compared to optimized sequences.
						The average T1 error and T2 error are computed for four regions of interest in the white matter and
						then averaged. These are standard deviations under the influence of gaussian noise, as computed by
						applying the bootstrap method of [RBB07] to in vivo data obtained from healthy volunteers.

table2.csv:	Systematic errors as predicted by the three-tissue digital phantom. Each voxel in the simulated brain
						is assigned to be either white matter (WM), grey matter (GM), or cerebrospinal fluid (CSF). The bloch
						equations are solved, and the resulting measurement outcomes are computed as in equation 11 of the supporting
						information using point spread functions that incorporate phase errors. The inferred values of T1 and T2
						are then computed from these signals for each voxel by dictionary matching. The root-mean-square deviation of
						the inferred value from the original value assigned to the voxels is tabulated for T1 for T2 for each
						of the three tissue types. sigma_j(T) is the RMS deviation in T_j for tissue type T, expressed in milliseconds.

table3.csv:	Here, digital phantom predictions are tabulated as in table 2 except that this model assumes no phase errors.

table4.csv:	For each of the three tissue types, the magnitude of the magnetization, as predicted by the Bloch equations, is
						averaged over the measurements (of which there is one for each TR). The minimum of these three numbers is recorded
						as "min mag". The quality factors for the three tissues are metrics of robustness against random error, which are
						estimated by a first order perturbative calculation in [KFH19, K18]. The noise model is identical independently
						distributed complex gaussian noise of mean zero and standard deviation sigma_eta added to the data point
						associated with each point in k-space, at each measurement. In this approximation, the predicted standard deviation
						in the value of T1 for grey matter due to random noise is given by sigma_eta sqrt[q_1(GM)], and similarly for
						T2 and for the other tissue types.


[RBB07]	M. J. Riffe, M. Blaimer, K. J. Barkausas, J. L. Duerk, and M. A. Griswold. SNR estimation
				in fast dynamic imaging using bootstrapped statistics. In Proceedings of the 15th Scientific
				Meeting, International Society for Magnetic Resonance in Medicine, page 1879, 2007.

[KFH19] Danielle Kara, Mingdong Fan, Jesse Hamilton, Mark Griswold, Nicole Sieberlich, and Robert
				Brown. Parameter map error due to normal noise and aliasing artifacts in MR fingerprinting.
				Magnetic Resonance in Medicine, 8(5):3108, 2019. doi:10.1002/mrm.27638.
				
[K18] 	Danielle Kara. Understanding error in magnetic resonance fingerprinting. PhD thesis, Case
				Western Reserve University, May 2018.
