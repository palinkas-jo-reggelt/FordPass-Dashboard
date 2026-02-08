# FordPass-Dashboard
A Home Assistant dashboard for the marq24/ha-fordpass FordPass integration (https://github.com/marq24/ha-fordpass).

This dashboard is almost "paste and forget" thanks to a variable created to plug the VIN using a trick I sorted out on AI. An example:

`{{ states('sensor.fordpass_' ~ states('input_text.ford_vin') ~ '_doorlock') }}`

The trick is to create an input_text helper and calling it “Ford VIN” (input_text.ford_vin) and putting the VIN into the text box. This allows the dashboard to repeatedly call the VIN for use without having to type/find/replace anything. It also makes updates a lot easier too.

The other requirement is the Mushroom cards from HACS.

Instructions:

1) Create `input_text.ford_vin` helper and input your VIN
2) Install Mushroom cards (required) if you don’t already have it
3) Create a new dashboard, go to edit in YAML, delete everything and paste in the code below.

Further customizaiton: To make the locks work as an actionable button, search and replace `entity: lock.fordpass_YOURVINHERE_doorlock` and put your VIN. Also, you can change the name of your car in the header using the visual editor.
