## The Computational Representation of Narratives

### Multipurpose Internet Mail Extensions

Inspired by the applicability of [Multipurpose Internet Mail Extensions (MIME)](https://en.wikipedia.org/wiki/MIME) to the [computational representation of arguments](https://github.com/AdamSobieski/Argumentation), could multipart MIME messages similarly be of use for the computational representation of narratives, actions, events, and updates to the [situation models](https://en.wikipedia.org/wiki/Narrative_paradigm#Situation_models) of modeled or simulated readers?

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
> --boundary-example
> 
> Content-ID: <metadata>
> Content-Type: text/turtle
> Content-Description: Message Metadata
> 
> @prefix dc: <http://purl.org/dc/terms/> .
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>  
> <mid:12345678> a n:NarrativeInterpretationEventMessage ;
>     dc:hasPart <cid:metadata>,
>         <cid:part1>,
>         <cid:part2>,
>         <cid:part3>,
>         <cid:part4>,
>         <cid:part5>,
>         <cid:part6> .
>
> --boundary-example
> 
> Content-ID: <part1>
> Content-Type: text/turtle
> Content-Description: Event Data
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>  
> <ex:event123> a n:NarrativeInterpretionEvent ;
>     n:agent <ex:char6> ;
>     n:patient <ex:prop126> ;
>     n:causesPatch <cid:part2>,
>         <cid:part3>,
>         <cid:part4>,
>         <cid:part5>,
>         <cid:part6> .
> 
> --boundary-example
> 
> Content-ID: <part2>
> Content-Type: text/ldpatch
> Content-Description: Interevent Causal Layer
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>  
> Add { <ex:event123> n:causedBy <ex:event122> . }
> 
> --boundary-example
> 
> Content-ID: <part3>
> Content-Type: text/ldpatch
> Content-Description: Scene Contents Layer
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>  
> Remove { <ex:scene114> n:containsProp <ex:prop126> . }
> 
> --boundary-example
> 
> Content-ID: <part4>
> Content-Type: text/ldpatch
> Content-Description: Scene Prop Description Layer
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>  
> Remove
> {
>     <ex:prop125> n:description "The bowl is filled with soup." ;
>         n:contains <ex:prop126> .
> }
> Add { <ex:prop125> n:description "The bowl is empty." . }
> 
> --boundary-example
> 
> Content-ID: <part5>
> Content-Type: text/ldpatch
> Content-Description: Intrapersonal Character Modeling Layer
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>  
> Remove { <ex:char6> n:hasState ex:Hungry . }
> Add { <ex:char6> n:hasState ex:Satiated . }
> 
> --boundary-example
> 
> Content-ID: <part6>
> Content-Type: text/ldpatch
> Content-Description: Interpersonal Social Modeling Layer
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>  
> --boundary-example--
> ```
> </details>

## See Also

* [Action](https://en.wikipedia.org/wiki/Action_(philosophy))
* [Causality](https://en.wikipedia.org/wiki/Causality)
* [Change](https://en.wikipedia.org/wiki/Impermanence)
* [Event](https://en.wikipedia.org/wiki/Event_(philosophy))
* [Narrative](https://en.wikipedia.org/wiki/Narrative)

## Related Work

* [IETF Structured Email Working Group](https://datatracker.ietf.org/group/sml/about/)
