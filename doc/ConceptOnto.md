# ConceptOnto

This page is under construction. Please bear. -Phanikumar, October 2020

Here we document the ontology ConceptOnto which builds on the [skos](http://www.w3.org/2004/02/skos/core) vocabulary. This ontology will represent the following aspects of Materials Domain: Materials Concepts, Material Behavior, Material Parameters, Tools, Techniques, Materials Processes and Material Defects. These are implemented as concept schemes. All the instances are organized in a hierarchy of concepts. The different classes defined in this ontology and the relationships will be detailed here. 

Following prefix is used for individuals in this page. All the instances in the ConceptOnto ontology will also be in this space. You can pick up the OWL file from here (under construction).

      PREFIX mc: <http://semantic.iitm.ac.in/ConceptOnto#>

Other prefixes used in this ontology are as follows.

      PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
      PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
      PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
      PREFIX owl: <http://www.w3.org/2002/07/owl#>
      PREFIX skos: <http://www.w3.org/2004/02/skos/core#>

## Classes
We use only two classes, namely skos:Concept and skos:ConceptScheme. Individuals in the name space mc: that correspond to concepts of various kind are instances of skos:Concept. Individuals in the name space mc: that correspond to the scheme of categorization are instances of skos:ConceptScheme.

The schemes of categorization are described below in detail.

### Materials Behavior
All concepts that come under Materials Behavior such as physical / chemical phenomena will be categorized under the following scheme.

     mc:MaterialsBehavior rdf:type skos:ConceptScheme

For example, solidification is a material behavior concept. This is expressed as:

     mc:Solidification rdf:type skos:Concept
     mc:Solidification skos:inScheme mc:MaterialsBehavior

Broader / narrower concepts are described using the skos vocabulary. For example:

     mc:AlloySolidification rdf:type skos:Concept
     mc:AlloySolidification skos:inScheme mc:MaterialsBehavior
     mc:AlloySolidification skos:broader mc:Solidification

The following instances are listed as top concepts for the scheme mc:MaterialsBehavior as points of entry for navigation.

     mc:MaterialsBehavior skos:hasTopConcept mc:Deformation
     mc:MaterialsBehavior skos:hasTopConcept mc:Diffraction
     mc:MaterialsBehavior skos:hasTopConcept mc:Diffusion
     mc:MaterialsBehavior skos:hasTopConcept mc:PhaseChange
     mc:MaterialsBehavior skos:hasTopConcept mc:ThermodynamicEquilibrium
     mc:MaterialsBehavior skos:hasTopConcept mc:TransportPhenomena

Any behavior that a material undergoes / exhibits can be listed in this scheme.

### Materials Concept

All concepts that indicate a physical understanding or representation of a behavior are captured in the scheme of categorization MaterialsConcept. 

      mc:MaterialsConcept rdf:type skos:ConceptScheme

For example, Bragg's law is a concept. This is expressed as:

      mc:BraggLaw rdf:type skos:Concept
      mc:BraggLaw skos:inScheme mc:MaterialsConcept
      mc:BraggLaw skos:broader mc:Laws

The following instances are listed as top concepts for the scheme mc:MaterialsConcept as points of entry for navigation.

      mc:MaterialsConcept skos:hasTopConcept mc:Criteria
      mc:MaterialsConcept skos:hasTopConcept mc:DimensionlessNumbers
      mc:MaterialsConcept skos:hasTopConcept mc:Effects
      mc:MaterialsConcept skos:hasTopConcept mc:Equations
      mc:MaterialsConcept skos:hasTopConcept mc:Laws
      mc:MaterialsConcept skos:hasTopConcept mc:Mechanisms
      mc:MaterialsConcept skos:hasTopConcept mc:Models
      mc:MaterialsConcept skos:hasTopConcept mc:Theorems
      mc:MaterialsConcept skos:hasTopConcept mc:Theory
      mc:MaterialsConcept skos:hasTopConcept mc:Relation
      mc:MaterialsConcept skos:hasTopConcept mc:Rules

Any theoretical knowledge that describes a material behavior or phenomenon can be listed in this scheme.

### Materials Defect

Defects that typically arise out of materials processing are listed under this scheme. 

      mc:MaterialsDefect rdf:type skos:ConceptScheme

For example, Chevron cracking is a defect that arises during extrusion process. This defect can be categorized as follows:

      mc:ChevronCracking rdf:type skos:Concept
      mc:ChevronCracking skos:inScheme mc:MaterialsDefect
      mc:ChevronCracking skos:broader mc:ExtrusionDefect

The following instances are listed as top concepts for the scheme mc:MaterialsDefect as points of entry for navigation.

      mc:MaterialsDefect skos:hasTopConcept mc:DrawingDefect
      mc:MaterialsDefect skos:hasTopConcept mc:ExtrusionDefect
      mc:MaterialsDefect skos:hasTopConcept mc:CastingDefect

### Materials Parameters

Parameters or variables of all kinds are listed under this scheme.

      mc:MaterialsParameters rdf:type skos:ConceptScheme

For example, Thermal Diffusivity is a Materials Parameter. This can be categorized as follows:

      mc:ThermalDiffusivity rdf:type skos:Concept
      mc:ThermalDiffusivity skos:inScheme mc:MaterialsParameter
      mc:ThermalDiffusivity skos:broader mc:ThermoPhysicalProperty

The following instances are listed as top concepts for the scheme mc:MaterialsParameters as points of entry for navigation.

      mc:MaterialsParameters skos:hasTopConcept mc:UniversalConstants
      mc:MaterialsParameters skos:hasTopConcept mc:Descriptor
      mc:MaterialsParameters skos:hasTopConcept mc:ProcessCondition
      mc:MaterialsParameters skos:hasTopConcept mc:ThermoPhysicalProperty

### Materials Processing

The hierarchy of materials processing techniques including manufacturing processes is categorized in this scheme.

      mc:MaterialsProcessing rdf:type skos:ConceptScheme

For example, GTAW is a Materials Processing concept. This can be categorized as follows:

      mc:GTAW rdf:type skos:Concept
      mc:GTAW skos:inScheme mc:MaterialsProcessing
      mc:GTAW skos:broader mc:ArcWelding

The following instances are listed as top concepts for the scheme mc:MaterialsProcessing as points of entry for navigation.

      mc:MaterialsProcessing skos:hasTopConcept mc:AdditiveProcesses
      mc:MaterialsProcessing skos:hasTopConcept mc:BulkDeformationProcesses
      mc:MaterialsProcessing skos:hasTopConcept mc:CastingProcesses
      mc:MaterialsProcessing skos:hasTopConcept mc:Grinding
      mc:MaterialsProcessing skos:hasTopConcept mc:HeatTreatment
      mc:MaterialsProcessing skos:hasTopConcept mc:HighEnergyRateForming
      mc:MaterialsProcessing skos:hasTopConcept mc:Machining
      mc:MaterialsProcessing skos:hasTopConcept mc:SheetMetalWorking
      mc:MaterialsProcessing skos:hasTopConcept mc:Welding

Any manufacturing process can be listed in this scheme under appropriate individual to preserve the hierarchy.

### Materials Technique

We understand the difference between a tool and a technique as follows: "A tool offers a technique that allows for determination of a parameter". A tool is like an experimental equipment or a computational software while a technique refers to the methodology employed by the tool to determine a materials parameter. 

Materials techniques are referred to be under the following scheme.

      mc:MaterialsTechnique rdf:type skos:ConceptScheme

For example, CALPHAD is a technique employed by software such as Thermo-Calc to calculate thermodynamic parameters.

      mc:CALPHAD rdf:type skos:Concept
      mc:CALPHAD skos:inScheme mc:MaterialsTechnique

The following instances are listed as top concepts for the scheme mc:MaterialsTechnique as points of entry for navigation.

      mc:MaterialsProcessing skos:hasTopConcept mc:DataAnalysis
      mc:MaterialsProcessing skos:hasTopConcept mc:CALPHAD
      mc:MaterialsProcessing skos:hasTopConcept mc:Measurement
      mc:MaterialsProcessing skos:hasTopConcept mc:SolutionOfPDE

Any procedure or methodology to calculate a parameter can be listed in this scheme.

### Materials Tool

A tool can be either Computational or Experimental in nature. All tools that are used to determine a materials parameter can be listed in this scheme.

      mc:MaterialsTool rdf:type skos:ConceptScheme

In this scheme, we list tools in a hierarchy as follows.

      mc:ThermoCalc rdf:type skos:Concept
      mc:ThermoCalc skos:inScheme mc:MaterialsTool
      mc:ThermoCalc skos:broader mc:ComputationalTools
      mc:DifferentialScanningCalorimeter rdf:type skos:Concept
      mc:DifferentialScanningCalorimeter skos:inScheme mc:MaterialsTool
      mc:DifferentialScanningCalorimeter skos:broader mc:ExperimentalTools

The following instances are listed a s top concepts for this scheme as points of entry for navigation.

      mc:MaterialsTool skos:hasTopConcept mc:ExperimentalTools
      mc:MaterialsTool skos:hasTopConcept mc:ComputationalTools

## Object properties

We have created 7 schemes of categorizing the concepts in the materials domain. If we wish to map every possible pair, the number of object relationship would be a large number. Here we define relations between those pairs of schemes that are most commonly related in materials domain.

The rationale for naming the relationships is as follows. We take the first two characters of the schemes in which the subject and object are categorized to create the name while the relation rdfs:label will point to the full name of the relationship. 

Eg., CoPa would be a name for the predicate (relationship) that would have **Co**ncept as subject and **Pa**rameter as object. Following is a list of relationships that are created in the name space mc: for convenience of relating various categories of concepts in this ontology.

I recommend that the relationship be mapped to the broadest concept possible. This is because, as you would see below, a super class axiom is used pass on the relationship to the concepts that are narrower to the object to which the original relationship is asserted. A reasoning engine such as Pellet would then provide the entailments as applicable. The section on transitive relations has examples to explain this better.

The Domain and Range for all the object properties we defined in this ontology is skos:Concept. 

### Concept + Parameter

Concepts have equations involving Parameters. 

      mc:CoPa rdfs:label "concept involved in equation for parameter"
      Source is a concept listed in scheme mc:MaterialsConcept
      Target is a concept listed in scheme mc:MaterialsParameter

For example, the concepts of non-dimensional numbers can be related to thermophysical parameters that are contained in them as follows.

      mc:BiotNumber mc:CoPa mc:ThermalConductivityOfSolid
      mc:FourierNumber mc:CoPa mc:ThermalDiffusivity

When rendered using the rdfs:label, the above to axioms would appear to be as follows:

      "Biot number" "concept involved in equation for parameter" "Thermal conductivity of solid"
      "Fourier number" "concept involved in equation for parameter" "Thermal diffusivity"

The inverse property is defined as follows.

      mc:PaCo rdfs:label "parameter involved in equation for concept"
      mc:PaCo owl:inverseOf mc:CoPa

### Concept + Behavior

Certain **Co**ncepts or equations or conditions are applicable during certain physical **Be**havior of materials. 

      mc:CoBe rdfs:label "concept is applicable during material behavior"

An example instance is as follows:

      mc:AvramiEquation mc:CoBe mc:PhaseChange
      mc:AbsoluteStabilityCriterion mc:CoBe mc:RapidSolidification

Conversely, a material **Be**havior could invole a certain **Co**ncept as per our understanding.

      mc:BeCo rdfs:label "material behavior could involve concept"
      mc:BeCo owl:inverseOf mc:CoBe

### Concept + Process

Concepts are related to certain processes. Conversely, a process could involve a certain concept.

      mc:isConceptRelatingToProcess has mc:Concept as Domain and mc:Process as Range
      mc:isProcessInvolvingConcept is an inverse of this property

### Parameter + Process

Processes are described by parameters. Conversely, parameters are conditions of certain processes.

      mc:isProcessConditionOf has mc:Parameters as Domain and mc:Process as Range
      mc:describedByParameter is an inverse of this property

### Process + Defect

Certain processes lead to certain defects. Conversely, certain defects form in certain processes.

      mc:leadsToDefect has mc:Process as Domain and mc:Defect as Range
      mc:formsInProcess is an inverse of this property

### Tool + Technique

Tools offer techniques. Conversely, techniques are offered by tools.

      mc:offersTechnique has mc:Tool as Domain and mc:Technique as Range
      mc:offeredByTool is an inverse of this property

### Technique + Parameter

Techniques provide for calculation or measurement of parameters. Conversely, parameter measurements are provided by certain techniques.

      mc:providesMeasurementOf has mc:Tecnique as Domain and mc:Parameters as Range
      mc:measurementProvidedBy is an inverse of this property

For example, calorimetry as a technique provides measurement of thermal properties such as heat capacity at constant pressure. This can be stated using the following triple.

      mc:Calorimetry mc:providesMeasurementOf mc:HeatCapacityAtConstantPressure

### Behavior + Process

Certain behavior of materials take place during certain processes. Conversely, certain processes involve certain behavior of materials.

      mc:takesPlaceDuring has mc:Behavior as Domain and mc:Process as Range
      mc:involves is an inverse of this property

For example, we can say that the directional behavior of solidication phenomenon takes place during a *process* such as Bridgmann technique. We should actually call it as Bridgmann process to be clear. This is expressed as a triple given below.

      mc:DirectionalSolidification mc:takesPlaceDuring mc:BridgmannTechnique

## Relationships of relationships

Property chains are relationships over relationships. We can navigate across the knowledge graph in longer hops by defining relationships over relationships. 

### Tool + Parameter 

We go from Tool to Parameter via Technique by defining the following property chain.

      mc:offersTechnique o mc:providesMeasurementOf -> offersTechniqueThatProvidesMeasurementOf
      mc:measurementProvidedByTechniqueOfferedByTool is an inverse of this property

For example, consider the following triples:

      mc:ThermoCalc mc:offersTechnique mc:CALPHAD
      mc:CALPHAD mc:providesMeasurementOf mc:HeatCapacityAtConstantPressure

when we use the Pellet reasoner, we can find the following inference as a triple:

      mc:ThermoCalc mc:offersTechniqueThatProvidesMeasurementOf mc:HeatCapacityAtConstantPressure

In plain English, this can be stated as follows: Thermo Calc is a tool that offers a technique CALPHAD using which one can calculate a parameter such as heat capacity at constant pressure.

## Equivalent classes

We can place instances in certain classes based on their properties. Once such class definitions are made, the reasoner will take care of placing the appropriate instances in the defined classes.

### Using Behavior to classify Concepts

Deformation concept is a class that contains all those concepts that have a property of being applicable during a physical behavior which is classified under deformation behavior. This is defined using the following statement.

      mc:DeformationConcept equivalent to mc:Concept and (mc:isApplicableDuring some mc:Deformation)

Using this definition, von Mises criterion can be classified under Deformation Concept because there is a property definition that says von Mises critrion is applicable during yielding which is places in the SubClass of Deformation under Behavior.

Similarly, Materials Characterization Concept is defined using the following definition. These can be expanded as we add more instances and their properties.

      mc:MaterialsCharacterizationConcept equivalent to mc:Concept and (mc:isApplicableDuring some mc:Diffraction)

Here are some more such definitions.

      mc:PhaseTransformationsConcept equivalent to mc:Concept and (mc:isApplicableDuring some mc:PhaseChange)
      mc:SolidificationConcept equivalent to mc:Concept and (mc:isApplicableDuring some mc:Solidification)
      mc:ThermodynamicsConcept equivalent to mc:Concept and (mc:isApplicableDuring some mc:ThermodynamicEquilibrium)
      mc:TransportPhenomenaConcept equivalent to mc:Concept and (mc:isApplicableDuring some mc:TransportPhenomena)


### Using Process to classify Defects

Defects can be classified under SubClasses based on the property mc:formsInProcess pointing to a SubClass under Processes. Following categories are defined using the equivalent class definitions listed below:
 
     mc:CastingDefects equivalent to mc:Defect and (mc:formsInProcess some mc:CastingProcesses)
     mc:DrawingDefect equivalent to mc:Defect and (mc:formsInProcess some mc:Drawing)
     mc:ExtrusionDefect equivalent to mc:Defect and (mc:formsInProcess some mc:Extrusion)
     mc:SandCastingDefect equivalent to mc:Defect and (mc:formsInProcess some ExpendableMoldCastingProcesses)

### Using Tool to classify Parameter

If a parameter is measured or calculated using a technique that is offered by a tool which is classified under Computational category, then one can call that parameter as a computable parameter. This is achieved using the following equivalent class defintion:

      mc:Computable equivalent to (mc:measurementProvidedByTechniqueOfferedByTool some mc:Computational)

Pellet would use this definition to infer that Liquidus Slope as a computable parameter because it is measured (calculated) using the CALPHAD technique which is offered by a tool, say, Thermo Calc that is categorized under the Computational type.

### Using Parameter to classify a Criterion

One can classify a criterion to be, say, digital criterion if it has an equation that involves a parameter inferred (from above) as computable. This is defined using the equivalent class definition as follows:

      mc:DigitalCriterion equivalent to (mc:hasEquationInvolving some mc:Computable)

Pellet would use this definition to infer that mc:ReynoldsNumber as a mc:DigitalCriterion because we have asserted that Reynolds number has an equation involving mass density which can be inferred (from above) as a computable parameter.


## The use of inverse relations

While navigating the knowledge graph, the inverse relations defined help in showing instances that one may not be looking for. Thus, ontologies help a learner discover more as they explore.
