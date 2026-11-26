# 🥇 My first feature
The first part of my Filtered Quest Board shows open photography assignments so Fico can see what work is available.

## 📋 My listings

```csv
id,side,what,description,when,price,unit,by,taken_by
g1,offer,Logo design,A simple two-color logo with one round of changes,Dec 1,80,dollars,Jordan,
g2,request,Logo design,A logo for our bake sale flyer,Dec 1,60,dollars,Alex,
g3,offer,Flyer text,Short catchy text for a one-page flyer,Nov 30,25,dollars,Casey,
g4,request,Flyer text,Upbeat words for our club flyer,Nov 30,30,dollars,Taylor,
g5,offer,Move-in help,Two strong arms for an hour on moving day,Sat 09:00,60,minutes,Sam,
g6,request,Spreadsheet lesson,Show me how to total a column and draw a chart,Tue 16:00,1,knowledge,Riley,
```
{: .dataset #listing }

[My listings](#)
{: .datagrid source="listing" #my_list columns="what, side, when, price, unit, by, taken_by" height="230" }

[One listing](#)
{: .form master="my_list" #one_listing editable="true" title="📝 One listing — pick it in the list" }

[🤝 Take it](#)
{: .button #take }
```python
listing = button.page.my_list.row
if not listing.taken_by:
    listing.taken_by = button.me()
```
{: .onclick }

## 🧪 My proof

```gherkin
Feature: Filtered Quest Board
  Scenario: I display the list
    When I display the list
    :::python
    self.list = getattr(self.page, "my_list", None)
    assert self.list, "no list yet — page 2 brings it"
    :::
    Then I see its listings
    :::python
    assert self.list.row_count > 0, "your list is empty — ask Bill for your listings, page 2"
    :::

  Scenario: I take one
    Given an open listing, picked in the list
    :::python
    self.list = getattr(self.page, "my_list", None)
    assert self.list, "no list yet — page 2 brings it"
    takers: list = [str(t or "").strip() for t in self.list.source.values("taken_by")]
    assert takers, "your list is empty — ask Bill for your listings, page 2"
    assert "" in takers, "every listing is taken already"
    self.list.select(takers.index("") + 1)
    :::
    When I take it
    :::python
    take = getattr(self.page, "take", None)
    assert take, "no 🤝 Take it button yet — page 3"
    take.click()
    :::
    Then it is taken
    :::python
    assert str(self.list.row.taken_by or "").strip(), "the listing is still open — your button wrote no name (signed in?)"
    :::
    Then it stays taken by the same person
    :::python
    first_taker = str(self.list.row.taken_by or "").strip()
    assert first_taker, "the listing has no taker after the first click"

    take = getattr(self.page, "take", None)
    assert take, "no 🤝 Take it button found for the second click"
    take.click()

    assert str(self.list.row.taken_by or "").strip() == first_taker, "the listing was retaken — second click changed the taker"
    :::
```
{: .feature #feature_01 visible="true" status="pending" }