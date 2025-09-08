# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
// DISCRETE FOURIER TRANSFORM 
clc;
clear;

// Take input discrete signal
x = input("Enter discrete signal as [x1 x2 ...]: ");
N = length(x);

// Initialize DFT output
X = zeros(1, N);

// DFT calculation using formula
for k = 0:N-1
    for n = 0:N-1
        X(k+1) = X(k+1) + x(n+1) * exp(-%i * 2 * %pi * k * n / N);
    end
end

// Frequency axis (normalized)
f = (0:N-1) / N;

// Plot magnitude and phase spectrum
subplot(2,1,1);
plot2d3(f, abs(X));
xtitle("Magnitude Spectrum of DFT");

subplot(2,1,2);
plot2d3(f, atan(imag(X), real(X))); // atan2 for phase
xtitle("Phase Spectrum of DFT");

# OUTPUT: ![WhatsApp Image 2025-09-08 at 15 34 57_a0d97873](https://github.com/user-attachments/assets/fa1ec310-d0ce-40d3-a70e-18cb97f80f42)



# RESULT: DFT and FFT of a given sequence in SCILAB is obtained

