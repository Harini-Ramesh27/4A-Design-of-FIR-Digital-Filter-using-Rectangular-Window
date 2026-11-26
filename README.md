# FIR-FILTER-DESIGN
# EXP 4 A: Design-of-FIR-Digital-Filter-using-Rectangular-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Rectangular-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clear;
close;

N = 21;               
wc = %pi / 2;         
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = wc / %pi;
    else
        hd(n+1) = sin(wc * (n - alpha)) / (%pi * (n - alpha));
    end
end

w = ones(1, N);      

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);

# OUTPUT: 
<img width="752" height="717" alt="image" src="https://github.com/user-attachments/assets/6d251f7b-9aaf-44f7-88b3-bdc9663b7dbe" />



# RESULT: 

Thus design of low pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc;
clear;
close;

N = 21;               
wc = %pi / 2;         
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = 1 - (wc / %pi);
    else
        hd(n+1) = -sin(wc * (n - alpha)) / (%pi * (n - alpha));
    end
end

w = ones(1, N);      

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);

# OUTPUT: 
<img width="755" height="722" alt="image" src="https://github.com/user-attachments/assets/04eae4d7-0c6e-42e5-8cd9-d9fea94e127e" />



# RESULT: 
Thus design of HIGH pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc;
clear;
close;

N = 21;               
wc1 = %pi / 4;        
wc2 = 3 * %pi / 4;    
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = (wc2 - wc1) / %pi;
    else
        hd(n+1) = (sin(wc2 * (n - alpha)) - sin(wc1 * (n - alpha))) / (%pi * (n - alpha));
    end
end

w = ones(1, N);      

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);

# OUTPUT: 
<img width="962" height="832" alt="image" src="https://github.com/user-attachments/assets/65dd3317-5eed-4dea-b7fc-6e9788486749" />



# RESULT: 
Thus design of BAND pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc;
clear;
close;

N = 21;               
wc1 = %pi / 4;        
wc2 = 3 * %pi / 4;    
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = 1 - ((wc2 - wc1) / %pi);
    else
        hd(n+1) = (sin(wc1 * (n - alpha)) - sin(wc2 * (n - alpha))) / (%pi * (n - alpha));
    end
end

w = ones(1, N);      

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);

# OUTPUT: 

<img width="952" height="797" alt="image" src="https://github.com/user-attachments/assets/ce725193-a719-426f-9d1f-35e8820cf015" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.
