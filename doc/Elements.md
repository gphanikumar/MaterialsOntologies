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

All properties defined in the pymatgen library for the periodic table of elements are mapped to a data property using the same name and datatype as far as possible. The data type chosen for the Range of the functions is also given along. The mapping is given in the following table.

| pymatgen property | Data Property | Range | Label |
| :---------  | :--------- | :----- | :----- |
| number | ae:number | xsd:integer | Atomic number |
| atomic_mass | ae:atomic_mass | xsd:float | Atomic mass |
| atomic_orbitals | ae:atomic_arbitals | RDF:Literal | Atomic orbitals |
| atomic_radius | ae:atomic_radius | xsd:float | Atomic radius in Angstroms |
| atomic_radius_calculated | ae:atomic_radius_calculated | xsd:float | Atomic radius calculated in Angstroms |
| average_anionic_radius | ae:average_anionic_radius | xsd:float | Average anionic radius in Angstroms |
| average_cationic_radius | ae:average_cationic_radius | xsd:float | Average cationic radius in Angstroms |
| average_ionic_radius | ae:average_ionic_radius | xsd:float | Average ionic radius in Angstroms |
| block | ae:block | rdfs:Literal | Block in the periodic table |
| boiling_point | ae:boiling_point | xsd:float | Boiling point in Kelvin |
| brinell_hardness | ae:brinell_harness | xsd:float | Brinell hardness in units of MN / m^2 |
| bulk_modulus | ae:bulk_modulus | xsd:float | Bulk modulus in units of GPa |
| coefficient_of_linear_thermal_expansion | ae:coefficient_of_linear_thermal_expansion | xsd:float | Coefficient of linear thermal expansion in units of K^-1 |
| common_oxidation_states | ae:common_oxidation_states | rdfs:Literal | List of common oxidation states |
| critical_temperature | ae:critical_temperature | xsd:float | Critical temperature |
| density_of_solid | ae:density_of_solid | xsd:float | Density of solid in units of kg / m^3 |
| electrical_resistivity | ae:electrical_resistivity | rdfs:Literal | Electrical resistivity with units as a string |
| X | ae:electronegativity | xsd:float | Pauling electronegativity |
| electronic_structure | ae:electronic_structure | rdfs:Literal | Electronic structure relative to a noble gas as a string |
| full_electronic_structure | ae:full_electronic_structure | rdfs:Literal | Full electronic structure as a string |
| group | ae:group | rdfs:Literal | Group in the periodic table as a character |
| ionic_radii | ae:ionic_radii | rdfs:Literal | Ionic radii as a string as printed for a list by pymatgen |
| is_actinoid | ae:is_actinoid | xsd:boolean | Boolean value True if the element is actinoid, else False |
| is_alkali | ae:is_alkali | xsd:boolean | Boolean value True if the element is alkali, else False |
| is_alkaline | ae:is_alkaline | xsd:boolean | Boolean value True if the element is alkaline, else False |
| is_halogen | ae:is_halogen | xsd:boolean | Boolean value True if the element is halogen, else False |
| is_lanthanoid | ae:is_lanthanoid | xsd:boolean | Boolean value True if the element is lanthanoid, else False |
| is_metalloid | ae:is_metalloid | xsd:boolean | Boolean value True if the element is metalloid, else False |
| is_noble_gas | ae:is_noble_gas | xsd:boolean | Boolean value True if the element is noble gas, else False |
| is_post_transition_metal | ae:is_post_transition_metal | xsd:boolean | Boolean value True if the element is post transition metal gas, else False |
| is_rare_earth_metal | ae:is_rare_earth_metal | xsd:boolean | Boolean value True if the element is rare earth metal, else False |
| long_name | ae:long_name | rdfs:Literal | Long name |



## Manually added properties

In addition two more properties are defined as follows. The boolean property is_pnictogen (not approved by IUPAC) is set to be True for elements in group 15 and False otherwise. The boolean property is_chalcogen is set to be True for elements in group 16 and False otherwise. The mapping is given in the following table.

| property | Data Property | Data type |
| :---------  | :--------- | :----- |
| pnictogen | ae:is_pnictogen | xsd:boolean |
| chalcogen | ae:is_chalcogen | xsd:boolean |


Please drop me a line if you find any issue with this mapping. 
