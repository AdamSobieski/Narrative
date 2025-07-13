## The Computational Representation of Narratives

### Multipurpose Internet Mail Extensions

Inspired by [uses of Multipurpose Internet Mail Extensions (MIME) with respect to the computational representation of argumentation](https://github.com/AdamSobieski/Argumentation), could MIME similarly be of use for the computational representation of narratives, events, and changes or updates to situation models?

> [!TIP]
> <details open>
> <summary>Click here to toggle the display of this example.</summary>
> <br>
> 
> ```email
> Message-ID: <12345678>
> Content-Type: multipart/related; boundary="boundary-example"
> Content-Metadata: <metadata>
> 
> --example-boundary
> 
> Content-ID: <metadata>
> Content-Type: text/turtle
> Content-Description: Message Metadata
> 
> ...
> 
> --example-boundary
> 
> Content-ID: <part1>
> Content-Type: text/turtle
> Content-Description: Event Data
> 
> <urn:event:123> a n:InterpretedEvent ;
>     <urn:event:123> n:actor <urn:char:6> .
> <urn:event:123> n:causesPatch
>     <cid:part2>,
>     <cid:part3>,
>     <cid:part4>,
>     <cid:part5>,
>     <cid:part6> .
> 
> --example-boundary
> 
> Content-ID: <part2>
> Content-Type: text/ldpatch
> Content-Description: Interevent Causal Layer
> 
> Add { <urn:event:123> n:causedBy <urn:event:122> . }
> 
> --example-boundary
> 
> Content-ID: <part3>
> Content-Type: text/ldpatch
> Content-Description: Scene Contents Layer
> 
> Remove { <urn:scene:114> n:containsProp <urn:prop:126> . }
> 
> --example-boundary
> 
> Content-ID: <part4>
> Content-Type: text/ldpatch
> Content-Description: Scene Prop Layer
> 
> Remove
> {
>     <urn:prop:125> n:description "The bowl is filled with soup." ;
>         n:contains <urn:prop:126> .
> }
> Add { <urn:prop:125> n:description "The bowl is empty." . }
> 
> --example-boundary
> 
> Content-ID: <part5>
> Content-Type: text/ldpatch
> Content-Description: Intrapersonal Character Modeling Layer
> 
> Remove { <urn:char:6> n:hasState ex:Hungry . }
> Add { <urn:char:6> n:hasState ex:Satiated . }
> 
> --example-boundary
> 
> Content-ID: <part6>
> Content-Type: text/ldpatch
> Content-Description: Interpersonal Social Modeling Layer
> 
> --example-boundary--
> ```
> </details>
