# 🐾 Adoption Day
Gabriel Perez
Play the tour
{: .avatar_trigger target="app_tour" }

```yaml
face:
  skin: "#e0ac69"
  hair: sides
  hair_color: "#4a3426"
  glasses: none
  wear: shirt
script:
  - do: read
    say: "Welcome to Adoption Day. Three campuses, and the sky over each one."
  - at: campus_grid
    do: select
    with: Racine
    say: "Pick Racine: the map flies south and checks the weather there, so volunteers can plan their walks."
  - at: campus_grid
    do: select
    with: Milwaukee
    say: "And back to Milwaukee. The forecast helps us choose a time when it is dry and not too hot for the dogs."
  - at: menu
    do: open
    with: Author
    say: "I'm Gabriel Perez and because of my skills I will be a billionaire."
  - do: read
stories: {}
```
{: .avatar #app_tour size="100" }

```
### 🌦 Walk
**Three campuses, one sky.** Pick a campus: the dogs go out when it is dry.

[Walk](#)
{: .runner src="../module_06/walk.md" bench="true" }

### 🙋 Author
## 💼 Hire me!

[My CV](#)
{: .runner src="../module_01/cv.md" bench="true" }
```
{: .tabs #menu }