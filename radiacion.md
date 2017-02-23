clc
#CONSTANTES
n=63;       #día del año
lt=19;      #Latitud
M=3;        #Minutos del día
t=365;

for i=1:t
  S=(23.5*sind(360*((284+i)/365)));  #ángulo declinación
  N=(2/15)*acosd(-tand(lt)*tand(S)); #Duración del día

  #Altura
  h=asind(sind(S)*sind(lt)+cosd(S)*cosd(lt)*cosd(0));

  #Ángulo horario
  H=(11.67*60/4)-(i-1);  
  
  #horas del día
  Hr=12-(H*4/60);

  #Altuta del sol
  hsol=1000*sind(asind(sind(-7.165)*sind(lt)+cosd(-7.165)*cosd(lt)*cosd(H)));
  L=[H,hsol];
  
  #plot(L(:,1), L(:,2),'o', "markersize", 5)
  #xlim([-24,24]);
  #ylim([-1000,1000]);
  #hsol=1000*sin(asin((sin(S)*sin(lt))+(cos(S)*cos(lt)*cos(H))));
endfor
