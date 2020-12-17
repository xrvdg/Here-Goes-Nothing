Here goes Nothing

- Seperation of concern and implementation:
  - Probleem
     - Abstractie op meerdere levels zorgt voor interferentie van concepten model en msg (Program flags model msg)
     - data types zijn active records
       - https://en.wikipedia.org/wiki/Active_record_pattern
       - Hoofdstuk uit Karwin, SQL anti patterns
  - Aanpak:
    - apart modeleren van wire protocol en domein
    - maybe's uit model datatypes
  - Alarmbellen:
    - overlappende nulpunten Maybe List, Maybe String
    - >1 Maybe aan linkerzijde van type
      - X  Maybe a -> ... -> Maybe b -> cm
  - Maybe als prototype techniek
    - Uitstellen van implementatie, niet uitstellen van keuze.
    - Functions delay binding; data structures induce binding. Moral: Structure data late in the programming process. http://www.cs.yale.edu/homes/perlis-alan/quotes.html
  - Next level
    - Datastructuren als Grammar
      - Grune, Parsing Techniques: A practical Guide
    - Sterkere theorieën en lemma maken combinators mogelijk.
    - Horn logica

computational trinitarianism
 - Heb je het al onder een andere hoek gehouden? https://extra.globo.com/incoming/5461346-810-e81/w448/xbeever-3.jpg.pagespeed.ic.MaMBrsEsy2.jpg
 - comp. trinitarianism = computational trinitarianism = propositions as types +programs as proofs +relation type theory/category theory
 - https://ncatlab.org/nlab/show/computational+trinitarianism
 - https://existentialtype.wordpress.com/2011/03/27/the-holy-trinity/

(general abstract) boolean blindness
- Either Result Maybe Optional
- Het is niet logisch maar toch wel, en vice versa.
    | A -> C, B -> D
    | A
    | ergo D
    WAT?!
  - het verschil verliezen tussen proves en entails
- https://github.com/quchen/articles/blob/master/algebraic-blindness.md
- https://existentialtype.wordpress.com/2011/03/15/boolean-blindness/
- maybe zijn te anoniem (Elm)
  - Richard Feldman video?

Philip Wadler: theorems for free
- https://scholar.google.com/scholar?cluster=6991272156635317390&hl=nl&as_sdt=0,5

(overlappende) nulpunten in datastructuren
- Just Just Just Nothing?! 
  - Maybe andThen andThen

- Nothing (filosofisch)
 - Close, Metaphysics: a very short introduction
 - Mumford, Nothing: a very short introduction
- Datastructuren als polynomen
 - stabiliteit van regelsystemen (analogie): https://web.mit.edu/2.14/www/Handouts/PoleZero.pdf
- Overlappende nulpunten
  - Maybe List -> List
  - Ergens in Simon Blackburn, Dictionary of Philosophy
    - Bertrand Rusell
    - negatie van existentieëlen (?)

Computionaliteit en Maybe's
  - partial and totallity
    - Martin Davis, The undecidables
    - John Harrison, Handbook of practical logic and automated reasoning
  - closure operator / gesloten ruimte
    - anders dan closures/thunks

- Combinators | SKI/lambda calculus
  * Raymond Smullyan: To mock a mock a mockingbird
  - SKI combinators
    - http://www.digizeitschriften.de/dms/img/?PID=GDZPPN002270110
  - Lambda
    - Hankin, Lambda calculi: A guide for computer scientists
    - Barendregt, The Lambda calculus (wiskundig)


- definierend programmeren / constructieve wiskunde / categorie theory / type theorie
  - logica
    - constructief, intuïtief
  - Personen
    - Yves Girard
    - De Bruijn
    - Heytinga
    - Arend
    - Barendregt
  - Programmeertalen
     - Agda | Idris
     - Haskell | Ocaml
  - Philosophy of Mathematics
    - Stewart Shapiro, Thinking about mathematics
  * Structuralism:
    https://en.wikipedia.org/wiki/Structuralism_(philosophy_of_mathematics)#Varieties



Verzin je eigen puntentelling:

type alias Object =
    { id : ObjectId
    , title : Maybe String
    , description : Maybe String
    , creators : List String
    , licence : Licence
    , source : Maybe String
    , objectNumber : Maybe String
    , organisationId : Maybe OrganisationId
    , entityType : EntityType
    , date : String
    , assets : List Asset
    , metadata : MetaData
    , rawData : Decode.Value
    , aiData : Maybe (List AiData)
    }

Smart constructor
mkObject : ReceivedObject -> Object


extensible records
 - Records: https://elm-lang.org/docs/advanced-topics
 - Daan lijen: http://research.microsoft.com/pubs/65409/scopedlabels.pdf
 - ^Puntentellingstrategie

extensible records (bonus)
 - techniek tegen explosie van subclasses
   - of higher kinds
   - Product of Sums en Sums of Products
     - Karnaugh Map
     - https://en.wikipedia.org/wiki/Algebraic_normal_form
