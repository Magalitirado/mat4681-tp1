# Commandes utilisées pour TP1 #

\***donnees est le nom de ma variable**\*

##Probleme 1##

####Question 1####
a)  `min(donnees$Debut)`= 1333.9, `max(donnees$Debut)`=1564.98,`median(donnees$Debut)` = 1475.745, `mean(donnees$Debut)`= 1476.514
			

b)  `hist(donnees$Debut, xlab="Valeur", ylab = "Fréquence", main = "Histogramme de l'indice S&P/TSX en début de journée")`

c)  `boxplot(donnees$Debut,horizontal = TRUE, xlab="Valeur",main = "Diagramme en moustache de l'indice S&P/TSX en début de journée")`

d)  `boxplot.stats(donnees$Debut,do.conf=TRUE, do.out=TRUE)` = donnees extremement faibles < 1374.060  et extremement hautes > 1564.980 <br>
`sum(donnees$Debut < 1374.060)` = 1 <br>

####Question 2####
a)  `min(donnees$Fin)`=1325.19, `max(donnees$Fin)` = 1565.15, `mean(donnees$Fin)` = 1476.142, `median(donnees$Fin)` = 1476.46

b) `hist(donnees$Fin, xlab="Valeur", ylab = "Fréquence", main = "Histogramme de l'indice S&P/TSX en fin de journée")`

c) `sd(donnees$Fin)`= 47.30821 donc les extremes sont si x < 1381.526 ou x > 1570.758. donc `sum(donnees$Fin < 1381.526)` = 6

d) `(sum(donnees$Fin > donnees$Debut*1.01) * 100) /250` = 11.6%

####Question 3####
2.33 est la valeur pour 0.98 de confiance
`mean(donnees$Debut) + 2.33 * sd(donnees$Debut)/sqrt(250)` et `mean(donnees$Debut) - 2.33 * sd(donnees$Debut)/sqrt(250)`, donc pour notre distribution, il y a 98% de probabilite que la moyenne se situe entre entre 1469.664 et 1483.363.

####Question 4####
2.33 est la valeur pour 0.98 de confiance
`mean(donnees$Fin) - 2.33 * sd(donnees$Fin)/sqrt(250)` et `mean(donnees$Fin) + 2.33 * sd(donnees$Fin)/sqrt(250)`, donc pour notre distribution, il y a 98% de probabilite que la moyenne se situe entre entre 1469.171 et 1483.114.


##Probleme 2##

####Question 1####
La proportion de fumeurs a 92% de chance de se trouver entre 0.2558942 et 0.3481510 :
`prop.test(x=90, n=300, p=0.3, alternative='two.sided', conf.level=0.92)`
La proportion de fumeuses a 92% de chance de se trouver entre 0.1780297 et 0.3378005 :
`prop.test(x=25, n=100, p=0.4, alternative='two.sided', conf.level=0.92)` 

####Question 2####


##Probleme 3##
`X1<-rnorm(3000, mean=400, sd=625)
X2<-rexp(3000, rate=10)`

####Question 1####
`hist(X1, right = FALSE, 
	main = "Histogramme du poids", xlab = "Poids",
	ylab = "Effectif", xlim=c(-3000,3000), ylim=c(0,1000),
	col = "darkolivegreen4")`
[Il manque le second graphique]

####Question 2####
a)  `quantile(X1, prob= c(0.25, 0.75))`
`quantile(X2, prob= c(0.25, 0.75))`

b)  X1 suit une loi normale de paramètre 400, 625 : 
`qnorm(0.25, mean=400, sd=sqrt(625))
qnorm(0.75, mean=400, sd=sqrt(25))`
Les quartiles théoriques sont 383.1378 et 416.8622.

X2 suit une loi exponentielle de paramètre 0.10 :
`qexp(0.25, rate=10)
qexp(0.75, rate=10)`
Les quartiles théoriques sont 0.0288 et 0.1386.

####Question 3####
a)  `pnorm(420, mean=400, sd=sqrt(625))-pnorm(380, mean=400, sd=sqrt(625))`= 0.5763

b)  

####Question 4####

####Question 5####
a)  `pth<-1-pexp(5/60, rate=10)` = 0.4346

b)  `matrice<-matrix(nrow=30, ncol=1000)
for(j in 1:1000){matrice[,j]<-rexp(30,rate=10)}
moyennes<-colMeans(matrice, dims=1)`
[Il manque la troisième étape]

c)  `par(mfrow=c(1,2))`
[Et ensuite je ne sais pas]
