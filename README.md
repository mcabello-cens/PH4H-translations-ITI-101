## ##

* Todos los request son GET.
* Si deseas usar POST, entonces mueve los parametros a un recurso Parameter y luego se invoca POST {{snowstorm}}/Concept/$translate 

## ANTECEDENTES LOCAL -> SNOMED ##

```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-antecedentes-local-to-racsel
&system=http://node-acme.org/terminology
&source=http://racsel.org/fhir/ValueSet/antecedentes-personales-local-vs
&target=http://racsel.org/fhir/ValueSet/antecedentes-personales-racsel-vs
&code=ant-1
```


## DIAGNOSTICOS LOCAL --> CIE-10 ##

```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-diagnosticos-local-to-cie10
&system=http://node-acme.org/terminology
&source=http://racsel.org/fhir/ValueSet/diagnosticos-local-vs
&target=http://racsel.org/fhir/ValueSet/cie10-vs
&code=dia-2
```


## ALERGIAS LOCAL --> SNOMED
```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-alergias-local-to-snomed
&system=http://node-acme.org/terminology
&source=http://racsel.org/fhir/ValueSet/alergias-local-vs
&target=http://racsel.org/fhir/ValueSet/alergias-vs
&code=ale-1
```


## VACUNAS LOCAL --> CIE11 ##
```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-vacunas-local-to-cie11
&system=http://node-acme.org/terminology
&source=
&target=
&code=vac-1
```


## VACUNAS LOCAL --> SNOMED ##
```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-vacunas-local-to-snomed
&system=http://node-acme.org/terminology
&source=http://racsel.org/fhir/ValueSet/vacunas-local-vs
&target=http://racsel.org/fhir/ValueSet/vacunas-vs
&code=vac-1
```

## VACUNAS PREQUAL --> SNOMED ##
```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-vacunas-prequal-to-snomed
&system=http://smart.who.int/pcmt-vaxprequal/CodeSystem/PreQualProductIDs
&source=http://racsel.org/fhir/ValueSet/vacunas-prequal-vs
&target=http://racsel.org/fhir/ValueSet/snomed-vs
&code=PolioVaccineOralOPVBivalProduct06bf2d06adcc6d9e2bea8ac21846bb09
```


## MEDICACION LOCAL --> SNOMED ##
```
{{snowstorm}}/ConceptMap/$translate
?url=http://racsel.org/fhir/ConceptMap/vs-medicacion-local-to-snomed
&system=http://node-acme.org/terminology
&source=http://racsel.org/fhir/ValueSet/medicacion-local-vs
&target=http://racsel.org/fhir/ValueSet/medicacion-vs
&code=med-1
```

## PROCEDIMIENTOS LOCAL --> SNOMED ##




