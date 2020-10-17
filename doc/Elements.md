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



