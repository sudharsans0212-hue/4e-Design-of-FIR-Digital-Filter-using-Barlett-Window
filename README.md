# FIR-FILTER-DESIGN
# EXP 4d: Design-of-FIR-Digital-Filter-using-Barlett-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Barlett-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```sci
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = Wc/ %pi ; 
else 
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2))/(M-1)); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR LPF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR LPF using Bartlett Window');
```

# OUTPUT: 

<img width="767" height="721" alt="image" src="https://github.com/user-attachments/assets/d8e405e1-2b6e-41e3-8d10-5cf7f6c29932" />

# RESULT: 

Thus design of low pass FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```sci
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = 1-Wc/ %pi ; 
else 
hd(n) = -sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1));  
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR HPF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR HPF using Bartlett Window');
```

# OUTPUT: 

<img width="770" height="723" alt="image" src="https://github.com/user-attachments/assets/ced27361-e2d1-403c-9b3c-d264e966246d" />

# RESULT: 
Thus design of HIGH pass FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```sci
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =(Wc2-Wc1)/%pi ; 
else 
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1)); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Bartlett Window');
```


# OUTPUT: 
<img width="528" height="456" alt="image" src="https://github.com/user-attachments/assets/ab6ef6ca-3014-441d-ab9e-59842806450f" />
<img width="757" height="721" alt="image" src="https://github.com/user-attachments/assets/7763a944-8780-49a2-99fa-2682dc4d1f80" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Barlettr-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```sci
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-((Wc2-Wc1)/%pi); 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1));  
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Bartlett Window');
```

# OUTPUT: 
<img width="594" height="509" alt="image" src="https://github.com/user-attachments/assets/b170663c-606d-4ba7-b5b1-e4f065946f13" />

<img width="755" height="716" alt="image" src="https://github.com/user-attachments/assets/0dd763ea-33cd-474d-ab02-57efd04dce10" />

# Manual Calculation

<img width="900" height="1600" alt="image" src="https://github.com/user-attachments/assets/d399f3a5-acca-4a7b-8ea2-2bfa4b11e2fb" />

# RESULT: 
Thus design of BAND STOP FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.
