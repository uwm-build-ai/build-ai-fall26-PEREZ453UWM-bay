# 🐾 Adoption Day

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
    say: "Welcome to Adoption Day. Check the weather at each campus to find a good time to walk the dogs."
  - at: campus_grid
    do: select
    with: Racine
    say: "Let's check Racine. The map moves south and gets the local forecast to help volunteers plan their walks."
  - at: campus_grid
    do: select
    with: Milwaukee
    say: "Now back to Milwaukee. We want a time when it is dry and not too hot for the dogs."
  - at: menu
    do: open
    with: Author
    say: "I'm Gabriel Perez. I built this in one semester, and I'm proud of being amazing at everything I do."
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