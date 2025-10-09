## General ##

* Todos los request son de tipo GET.
* Si deseas usar POST, entonces mueve los parametros a un recurso Parameter y luego se invoca POST {{snowstorm}}/Concept/$translate
* la url del CodeSystem usada es http://node-acme.org/terminology. En tu caso debes usar la URL asignada
* Ejemplo:
  * Colombia -> http://node-CO.org/terminology
  * Argentina -> http://node-AR.org/terminology

### Pasos para construir un request translate: ###
1. Busca en tu servidor terminologico un ConceptMap para la traducción requerida
2. En el servidor el nombre de los ConceptMaps da entrega una indicación de que elementos puede traducir. Verás algo asi como VSVacunasLocalToSnomed, VSAntecedentesLocalToCIE10.
3. Abre el ConceptMap y rescata **url** y  los url valueSet los atributos **sourceUri** y **targetUri**. Usarás estos parámetros para construir el $translate
4. Si tienes dudas del contenido de un valueset del paso anterior, puedes hacer un $expand para retornar el conjunto de codigos
   * GET {{snowstorm}}/ValueSet/$expand?url=http://racsel.org/fhir/ValueSet/antecedentes-personales-local-vs
5. Agrega el codigo del concepto (**code**) y su url (**system**) de codesystem subyacente.

Ejemplo:

<img width="530" height="483" alt="image" src="https://github.com/user-attachments/assets/812bc044-6e1e-4cb4-af07-f53b590424c9" />


## Traducciones de codigos locales hacia otras terminologías ##

### ANTECEDENTES LOCAL => SNOMED ###

```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-antecedentes-local-to-racsel
&system=http://node-acme.org/terminology
&source=http://racsel.org/fhir/ValueSet/antecedentes-personales-local-vs
&target=http://racsel.org/fhir/ValueSet/antecedentes-personales-racsel-vs
&code=ant-1
```


### DIAGNOSTICOS LOCAL => CIE-10 ###

```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-diagnosticos-local-to-cie10
&system=http://node-acme.org/terminology
&source=http://racsel.org/fhir/ValueSet/diagnosticos-local-vs
&target=http://racsel.org/fhir/ValueSet/cie10-vs
&code=dia-2
```


### ALERGIAS LOCAL => SNOMED
```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-alergias-local-to-snomed
&system=http://node-acme.org/terminology
&source=http://racsel.org/fhir/ValueSet/alergias-local-vs
&target=http://racsel.org/fhir/ValueSet/alergias-vs
&code=ale-1
```


### VACUNAS LOCAL => CIE11 ###
```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-vacunas-local-to-cie11
&system=http://node-acme.org/terminology
&source=
&target=
&code=vac-1
```


### VACUNAS LOCAL => SNOMED ###
```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-vacunas-local-to-snomed
&system=http://node-acme.org/terminology
&source=http://racsel.org/fhir/ValueSet/vacunas-local-vs
&target=http://racsel.org/fhir/ValueSet/vacunas-vs
&code=vac-1
```

### VACUNAS PREQUAL => SNOMED ###
```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-vacunas-prequal-to-snomed
&system=http://smart.who.int/pcmt-vaxprequal/CodeSystem/PreQualProductIDs
&source=http://racsel.org/fhir/ValueSet/vacunas-prequal-vs
&target=http://racsel.org/fhir/ValueSet/snomed-vs
&code=PolioVaccineOralOPVBivalProduct06bf2d06adcc6d9e2bea8ac21846bb09
```


### MEDICACION LOCAL => SNOMED ###
```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-medicacion-local-to-snomed
&system=http://node-acme.org/terminology
&source=http://racsel.org/fhir/ValueSet/medicacion-local-vs
&target=http://racsel.org/fhir/ValueSet/medicacion-vs
&code=med-1
```

### PROCEDIMIENTOS LOCAL => SNOMED ###
```
http://192.168.10.18:8180/fhir/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-procedimientos-local-to-snomed
&system=http://node-acme.org/terminology
&source=http://racsel.org/fhir/ValueSet/procedimientos-local-vs
&target=http://racsel.org/fhir/ValueSet/procedimientos-vs
&code=pro-2
```


