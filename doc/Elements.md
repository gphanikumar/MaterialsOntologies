# Elements

Here we document the ontology Elements which captures the properties of periodic table of elements as described in the python library [pymatgen](https://pymatgen.org/).

In this document the following prefixes are used:

      @PREFIX owl: <http://www.w3.org/2002/07/owl#>
      @PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
      @PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
      @PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>

The OWL files are available at the following locations:
  * [semantic.iitm.ac.in](http://semantic.iitm.ac.in/AlloyOnto/Elements/)
  * [Asserted Axioms](../files/elements-asserted.owl)
  * [Inferred Axioms](../files/elements-inferred.owl)

The namespace used for the individuals and properties in this ontology is as follows:

     @PREFIX ae: <http://semantic.iitm.ac.in/AlloyOnto/Elements#>

The class defined to hold all the elements is with the IRI:

     ae:Elements

Each element is created as an individual in this namespace. Examples are:

     ae:Cu a ae:Elements
     ae:Ni a ae:Elements

In addition, individuals with long names have also been created and mapped over to the corresponding individuals with symbol names using the relationship owl:sameAs.

     ae:Copper owl:sameAs ae:Cu
     ae:Nickel owl:sameAs ae:Ni

## Properties mapped from pymatgen

All properties defined in the pymatgen library for the periodic table of elements are mapped to a data property using the same name and datatype as far as possible. The mapping is given in the following table.

| pymatgen property | Data Property | Data type | Label |
| :---------  | :--------- | :----- | :----- |
| number | ae:number | xsd:integer | Atomic number |
| atomic_mass | ae:atomic_mass | xsd:float | Atomic mass |
| atomic_orbitals | ae:atomic_arbitals | RDF:Literal | Atomic orbitals |
| atomic_radius | ae:atomic_radius | xsd:float | Atomic radius |
| long_name | ae:long_name | rdfs:Literal | Long name |



## Manually added properties

In addition two more properties are defined as follows. The boolean property is_pnictogen (not approved by IUPAC) is set to be True for elements in group 15 and False otherwise. The boolean property is_chalcogen is set to be True for elements in group 16 and False otherwise. The mapping is given in the following table.

| property | Data Property | Data type |
| :---------  | :--------- | :----- |
| pnictogen | ae:is_pnictogen | xsd:boolean |
| chalcogen | ae:is_chalcogen | xsd:boolean |


Please drop me a line if you find any issue with this mapping. 
