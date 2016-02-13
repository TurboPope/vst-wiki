# Eclipse Modeling Framework

**Eclipse Modeling Framework** (EMF) is an Eclipse-based modeling framework and code generation facility for building tools and other applications based on a structured data model.

From a model specification described in XMI, EMF provides tools and runtime support to produce a set of Java classes for the model, a set of adapter classes that enable viewing and command-based editing of the model, and a basic editor. Models can be specified using annotated Java, UML, XML documents, or modeling tools, then imported into EMF. Most important of all, EMF provides the foundation for interoperability with other EMF-based tools and applications

**Ecore** is the core (meta-)model at the heart of EMF. It allows expressing other models by leveraging its constructs. Ecore is also its own metamodel (i.e.: Ecore is defined in terms of itself).

(*Quelle:* [Wikipedia](https://en.wikipedia.org/wiki/Eclipse_Modeling_Framework))


# Graphical Editing Framework
> The Graphical Editing Framework (GEF) provides technology to create rich graphical application. (*Quelle:* <https://eclipse.org/gef/>)

Das GEF ist eine Alternative zum EMF. Das GEF stellt Modelle grafisch dar und erlaubt deren Manipulation. Ist kostengünstige möglichkeit für MDD, hält Modelle konsistent und erspart Programmieraufwand. Es ist allerdings nicht so mächtig wie UML, da es nur auf **Essential MOF** basiert, einem Subset des MOF.
