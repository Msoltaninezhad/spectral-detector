# spectral-detector
with this code you can find desire spectra of a image (the detector was ccd in our work)
function [A1] = spectraldetector
A = imread('ebsnofiterbaft.png');
figure,imshow(A)
Ared=A(:,:,1);
Agreen=A(:,:,2);
Ablue=A(:,:,3);
Agray=rgb2gray(A);
Grayscale = input('Do you want it in grayscale?'); % if you want grayscale img chose 1
if Grayscale == 1
figure,imshow(Agray)
u=input('please enter desire line for spectroscopy'); %u reperesent x line here you can find desire line for spectra 
Ag=Agray(:,u);


x = 1:length(Ag);
figure,scatter(x,Ag);
title('spectra');

xlabel('degree')
ylabel('intensity')
end
Spectral = input('what color spectral do you want?'); %red=1 green=2 blue=3 
if Spectral==1
    figure,imshow(Ared)
    
elseif Spectral==2
    figure,imshow(Ablue)
    
elseif Spectral==3
    figure,imshow(Agreen)
    
end

i=input('please enter desire line for spectroscopy'); %i reperesent x line here you can find desire line for spectra 
A1=Ared(:,i);
A1=Ablue(:,i);
A1=Agreen(:,i);

x = 1:length(A1);
figure,scatter(x,A1);
title('spectra');
xlabel('degree')
ylabel('intensity')

end
