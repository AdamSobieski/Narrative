## The Computational Representation of Narratives

### Multipurpose Internet Mail Extensions

Inspired by the applicability of [Multipurpose Internet Mail Extensions (MIME)](https://en.wikipedia.org/wiki/MIME) to the [computational representation of arguments](https://github.com/AdamSobieski/Argumentation), could multipart MIME messages similarly be of use for the computational representation of narratives, actions, events, processes, and updates to the [situation models](https://en.wikipedia.org/wiki/Narrative_paradigm#Situation_models) of modeled and simulated readers?

> [!TIP]
> This preliminary example shows a model of a story event (`ex:event123`) involving a story character (`ex:char6`) having consumed all of the soup (`ex:prop126`) from a bowl (`ex:prop125`).
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
>  
> <mid:12345678> a n:StoryEventMessage ;
>     dc:hasPart <cid:metadata>,
>         <cid:part1>,
>         <cid:part2>,
>         <cid:part3>,
>         <cid:part4>,
>         <cid:part5>,
>         <cid:part6>,  
>         <cid:part7>,
>         <cid:part8>,  
>         <cid:part9>,
>         <cid:part10> .
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
> <ex:event123> a n:StoryEvent ;
>     n:causesPatch <cid:part2>,
>         <cid:part3>,
>         <cid:part4>,
>         <cid:part5>,
>         <cid:part6>,  
>         <cid:part7>,
>         <cid:part8>,  
>         <cid:part9>,
>         <cid:part10> .
> 
> --boundary-example
> 
> Content-ID: <part2>
> Content-Type: text/ldpatch
> Content-Description: Plot Layer
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>  
> Add {
>     ex:char6 n:performed ex:action29 .
>     ex:event123 n:causedBy ex:action29 .
> }
> 
> --boundary-example
> 
> Content-ID: <part3>
> Content-Type: text/ldpatch
> Content-Description: Props Layer
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>  
> Remove { ex:prop125 ex:contains ex:prop126 . }
> 
> --boundary-example
> 
> Content-ID: <part4>
> Content-Type: text/ldpatch
> Content-Description: Character Modeling Layer (States and Traits)
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>  
> Remove { ex:char6 n:hasState ex:Hungry . }
> Add { ex:char6 n:hasState ex:Satiated . }
> 
> --boundary-example
>
> Content-ID: <part5>
> Content-Type: text/ldpatch
> Content-Description: Intrapersonal Character Modeling Layer (Beliefs)
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>
> --boundary-example
>
> Content-ID: <part6>
> Content-Type: text/ldpatch
> Content-Description: Intrapersonal Character Modeling Layer (Desires)
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>
> Remove { ex:char6 n:desires ex:prop126 . }
> 
> --boundary-example
>
> Content-ID: <part7>
> Content-Type: text/ldpatch
> Content-Description: Intrapersonal Character Modeling Layer (Intentions)
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>
> Remove { ex:char6 ex:intends ex:action29 . }
> 
> --boundary-example
>
> Content-ID: <part8>
> Content-Type: text/ldpatch
> Content-Description: Intrapersonal Character Modeling Layer (Emotions and Moods)
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>
> --boundary-example
>
> Content-ID: <part9>
> Content-Type: text/ldpatch
> Content-Description: Intrapersonal Character Modeling Layer (Thoughts)
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
>
> --boundary-example
> 
> Content-ID: <part10>
> Content-Type: text/ldpatch
> Content-Description: Interpersonal Modeling Layer (Social Dynamics)
> 
> @prefix n: <http://narratology.org/#> .
> @prefix ex: <http://example.org/#> .
> 
> --boundary-example--
> ```
> </details>

### Inferences During Reading Comprehension

> [!TIP]
> The following table is from Graesser, Singer, and Trabasso (1994) and presents 13 classes of inferences which do not exhaust all of the potential inferences during [comprehension](https://en.wikipedia.org/wiki/Reading_comprehension) but, instead, provide an initial foundation for discussing the [constructivist theory](https://en.wikipedia.org/wiki/Constructivism_(psychological_school)).
> <details open>
> <summary>Click here to toggle the display of this table.</summary>
> <br>
> 
> | Type of Inference | Brief Description |
> |-------------------|-------------------|
> | Referential | A word or phrase is referentially tied to a previous element or constituent in the text (implicit or inferred) |
> | Case Structure Role Assignment | An explicit noun phrase is assigned to a particular case structure role, e.g., agent, recipient, object, location, time |
> | Causal Antecedent | The inference is on a causal chain (bridge) between the current explicit action, event, or state and the previous passage context |
> | Superordinate Goal | The inference is a goal that motivates an agent's intentional action |
> | Thematic | This is a main point or moral of the text |
> | Character Emotional Reaction | The inference is an emotion experienced by a character, caused by or in response to an event or action |
> | Causal Consequence | The inference is on a forecasted causal chain, including physical events and new plans of agents (excluding character emotions) |
> | Instantiation of Noun Category | The inference is a subcategory or a particular exemplar that instantiates an explicit noun or an implicit case role that is required by the verb |
> | Instrument | The inference is an object, part of the body, or resource used when an agent executes an intentional action |
> | Subordinate Goal Action | The inference is a goal, plan, or action that specifies how an agent's action is achieved |
> | State | The inference is an ongoing state, from the time frame of the text, that is not causally related to the story plot. The states include an agent's traits, knowledge, and beliefs; the properties of objects and concepts; and the spatial locations of entities |
> | Emotion of Reader | The inference is the emotion that the reader experiences when reading a text |
> | Author's Intent | The inference is the author's attitude or motive in writing |
> </details>

> [!TIP]
> The following table, also from Graesser, Singer, and Trabasso (1994), presents six production rules of the constructivist theory which model the process of explanation and establishing global coherence.
> <details open>
> <summary>Click here to toggle the display of this table.</summary>
> <br>
> 
> | Production Rule | Conditions | Succinct Description of Cognitive Process | Elaborated Description of Cognitive Processes |
> |:---------------:|------------|-------------------------------------------|-----------------------------------------------|
> | A | Explicit statement in the discourse focus is an intentional action (A) or goal (G) of a character | Explain why the character performed action A or has goal G | <ol><li>Search information sources in WM and LTM for plausible superordinate goals of A or G.</li><li>Increase the activation of superordinate goals in WM to the extent that (a) they are in multiple information sources and (b) they are compatible with the constraints of WM content that meet fomr threshold of activation.</li></ol> |
> | B | Explicit statement in the discourse focus is an intentional action (A), a goal (G), or an event (E) | Explain why the character performed action A, why the character has goal G, or why event E occurred | <ol><li>Search information sources in WM and LTM for plausible causal antecedents of A, G, or E.</li><li>increase the activation of the causal antecedents in WM to the extent that (a) they are in multiple information sources and (b) they are compatible with the constraints of WM content that meet some threshold of activation.</li></ol> |
> | C | Any explicit statement (S) in the discouse focus | Explain why the writer mentions S | <ol><li>Search text genre schemas in LTM that would accomodate S.</li><li>Increase the activation of the genre schema to the extent that it is compatible with the constraints of S and with WM content that meets some threshold of activation.</li></ol> |
> | D | Explicit statement in the discourse focus is an intentional action (A) or an event (E) | Track the emotional reactions of characters | <ol><li>Search information sources in WM and LTM for salient emotional reactions of characters to A or E.</li><li>Increase the activation of the emotional reactions in WM to the extent that (a) they are in multiple information sources and (b) they are compatible with the constraints of WM content that meet some threshold of activation.</li></ol> |
> | E | WM contains a particular configuration (C) of goals, actions, events, emotions, and/or states that meet some threshold of activation | Create global structures | <ol><li>Search for information sources in LTM that match configuration C.</li><li>Increase the activation of the information source in WM to the extent that it is compatible with the constraints of WM content that meet some activation threshold.</li></ol> |
> | F | An implicit statement or structure in WM meets some activation structure | Construct inferences that receive high activation in WM | The implicit statement structure is constructed as an inference in the situation model. |

## See Also

* [Action](https://en.wikipedia.org/wiki/Action_(philosophy))
* [Belief](https://en.wikipedia.org/wiki/Belief)
* [Causality](https://en.wikipedia.org/wiki/Causality)
* [Change](https://en.wikipedia.org/wiki/Impermanence)
* [Constructivism](https://en.wikipedia.org/wiki/Constructivism_(psychological_school))
* [Desire](https://en.wikipedia.org/wiki/Desire)
* [Event](https://en.wikipedia.org/wiki/Event_(philosophy))
* [Goal](https://en.wikipedia.org/wiki/Goal)
* [Intention](https://en.wikipedia.org/wiki/Intention)
* [Narrative](https://en.wikipedia.org/wiki/Narrative)
* [Plot](https://en.wikipedia.org/wiki/Plot_(narrative))
* [Process](https://en.wikipedia.org/wiki/Process)
* [Process Philosophy](https://en.wikipedia.org/wiki/Process_philosophy)
* [Social Relation](https://en.wikipedia.org/wiki/Social_relation)
* [Theme](https://en.wikipedia.org/wiki/Theme_(narrative))

## Related Work

* [IETF Structured Email Working Group](https://datatracker.ietf.org/group/sml/about/)
