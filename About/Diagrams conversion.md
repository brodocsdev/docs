



# Diagrams

To have the diagram generated, commit the source file to the source repository and refer to it as image link:
```plain
![](/testSequence.png)
![](/testDrawio.png)
```

Supported are [Plant UMLs](https://crashedmind.github.io/PlantUMLHitchhikersGuide/) (also c4) and draw.io. You may prefer plant uml over draw.io since they human readable so you can get feedback in pull request. Even more readable when you keep the formatting in separate file and !include it. The same goes for AI agents, they can digest plant umls quite well.

When working in editor (VSC, Idea), you can generate the files locally without committing just to see the final text and generated images in markdown preview before pushing to repository. 

Draw.io support is experimental, it takes much more resources to generate than generating plant uml even for very simple diagram.


## Example sequence
[Source](https://github.com/brodocsdev/docs/blob/main/testSequence.puml)

![](/testSequence.png)


```plain
![](/testSequence.png)
```


## Example component
[Source](https://github.com/brodocsdev/docs/blob/main/componentExample.puml)

![](/componentExample.png)


```plain
![](/tcomponentExample.png)
```


## Example c4
[Source](https://github.com/brodocsdev/docs/blob/main/c4.puml)

![](/c4.png)


```plain
![](/c4.png)
```

