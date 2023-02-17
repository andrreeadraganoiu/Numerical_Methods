312CD Draganoiu Andreea

TEMA 1 MN
1.Interpolare nearest-neighbour
	->nn_2x2 - Rotunjesc prima jumatate a intervalului x_int la 1 si a doua
		jumatate la 2, la fel si pentru y_int.
	->nn_2x2_RGB - Extrag a treia dimensiune a img pentru a determina culoarea, iar 
		apoi unesc cele 3 canale rezultate
	->nn_resize - Am urmat intocmai TODO -urile. Axele sunt inversate, iar de aceea
		am apelat R(y+1,x+1).Am adaugat o unitate pentru ca operatiile incep
		de la 0
	->nn_resize_RGB - analog cu nn_2x2_RGB

2.Interpolare bilineara
	->bilinear_coef - Determin matricea coeficientilor cu mentiunea ca f din 
		matricea b va avea coordonatele inversate, cum sunt de altfel si axele.
	->bilinear_2x2 - Calculez valoarea pixelului cu formula plasata in PDF.
	->bilinear_2x2_RGB - analog cu nn_2x2_RGB, nn_resize_RGB.
	->bilinear_resize - Calculez punctele x1,x2,y1,y2 astfel incat coordonatele
		sa nu depaseasca chenarul pentru a afla coeficientii si a aplica formula
		de la 2x2
	->bilinear_resize_RGB - analog cu nn_2x2_RGB, nn_resize_RGB, bilinear_2x2_RGB
	->bilinear_rotate - Am verificat cazul in care x_p si y_p se afla in afara
		imaginii si am pus negru(0) in matricea finala.
	->bilinear_rotate_RGB - analog cu nn_2x2_RGB


3.Interpolare bicubica
	->precalc_d - Calculez derivatele evitand colturile(vor fi 0 in matrice).
		Inversez formulele de calcul pentru fx si fy pentru ca imaginea are
		axele inversate.
	->bicubic_coef - Inmultesc matricele din PDF, cu coordonatele pentru f inversate
	->bicubic_resize - Calculez punctele x1,x2,y2,y2 pentru a afla matricea de 
		coeficienti si folosesc formula
	->bicubic_resize_RGB - analog cu nn_2x2_RGB

 
