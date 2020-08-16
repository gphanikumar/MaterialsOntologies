# ConceptOnto

Here we document the ontology ConceptOnto. This ontology will represent the following aspects of Materials Domain: Concepts, Behavior, Parameters, Tools, Techniques, Processes and Defects. The different classes defined in this ontology and the relationships will be detailed here. 

Following prefix is used for individuals in this page.

      PREFIX mc: <http://semantic.iitm.ac.in/ConceptOnto/MaterialsConcepts#>

## Classes
All instances in the ontology ConceptOnto will fall into the following classes.
Equivalent class definitions are defined based on certain relationships as described below.

### Behavior
The class mc:Behavior has instances that indicate behavior of materials such as physical phenomena. For example:

      mc:AlloySolidification is an instance under the class mc:Behavior

As of now, instances are defined under SubClasses such as Cracking, Deformation, Diffraction, Diffusion, Fluid Flow, Heat Transfer, Mass Transfer, Phase Change, Reaction, Thermodynamic Equilibrium and Transport Phenomena.

Transport Phenomena is a SubClass which is a union of Diffusion, Fluid Flow, Heat Transfer, Mass Transfer and Reaction.

### Concept
The class mc:Concept has instances that indicate a physical understanding or representation of a behavior. SubClasses defined are Criterion, Dimensionless Number, Effects, Equation, Instability, Laws, Mechanism, Model, Paradox, Principles, Relation, Rules, Theorem and Theory. For example:

      mc:AbsoluteStabilityCriterion is an instance under the class mc:Concept

### Defect
The class mc:Defect has instances that indicate a defect that arises typically due to processing. For example:

      mc:ChevronCracking is an instance under the class mc:Defect

### Parameters
The class mc:Parameters has instances that indicate parameters, variables, constants and process conditions that are useful in describing a process or in defining concept or an equation. For example:

      mc:MassDensity is an instance under the class mc:Parameters
      mc:GrainSize is an instance under the class mc:Parameters

As for now, parametesr are organized in Subclasses such as Empirical, Measured Quantity, Model Parameter, Physical Property, Process Condition, Thermodynamic Property and Universal Constants.

### Process
The class mc:Process has instances that indicate different processing techniques used in the materials domain. For example:

      mc:InvestmentCasting is an instance under the class mc:Process

As of now, processes are organized in SubClasses such as Bulk Deformation Processes, Casting Processes, Grinding Processes, High Energy Rate Forming, Machining, Sheet Metal Working and Welding.

### Technique
The class mc:Technique has instances that indicate a way to use a tool to calculate or experimentally measure a parameter. For example:

      mc:CALPHAD is an instance under the class mc:Technique

### Tool
The class mc:Tool has instances that can be either Computational or Experimental in nature. The instances are organized under these two SubClasses for convenience. For example:

      mc:ThermoCalc is an instance under the classes mc:Tool and mc:ComputationalThermodynamics
      mc:OpticalMicroscope is an instance under the classes mc:Tool and mc:Experimental

## Object properties

### Concept + Parameter
Concepts have equations involving parameters. Conversely, a parameter is involved in the equation for a concept.

      mc:hasEquationInvolving has mc:Concept as Domain and mc:Parameters as Range
      mc:isInvolvedInEquationFor is an inverse of this property.

If we want to state that the concept of Hall-Petch equation involves grain size, we can use the following triple.

      mc:HallPetchRelationship mc:hasEquationInvolving mc:GrainSize


### Concept + Behavior
Certain concepts or equations or conditions are applicable during certain physical behavior of materials. Conversely, a behavior could invole a certain concept as per our understanding.

      mc:isApplicableDuring has mc:Concept as Domain and mc:Behavior as Range
      mc:couldInvove is an inverse of this property.

If we wish to state that the absolute stability criterion for planar solidification is applicable during rapid solidification behavior, we can use the following triple.

      mc:AbsoluteStabilityCriterion mc:isApplicableDuring mc:RapidSolidification

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
