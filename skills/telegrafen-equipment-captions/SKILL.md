---
name: telegrafen-equipment-captions
description: Use when writing, rewriting, or QAing Norwegian Bokmål captions (bildetekst) and alternative text (alt-tekst) for Telenor equipment images in the Enhetsbibliotek (routers, ONT, forsterkere, modem, antenner, TV-bokser, fjernkontroller, kabler, veggkontakter), including the Equipment captions Figma document and the Image caption component.
metadata:
  version: "0.1 draft"
---

# Telegrafen equipment captions v0.1 (draft)

Writes captions and alt text for equipment images so they meet WCAG 2.2 AA and EN 301 549. Write the skill and its rules in English; only the produced captions, alt text and examples are Norwegian Bokmål. Use `telegrafen-ux-writing` for tone of voice. Output is a draft until the product team has fact-checked it.

## Requirements

- WCAG 1.1.1 Non-text Content is unchanged in WCAG 2.0, 2.1 and 2.2. Meaningful images need a text alternative; decorative images get an empty alt.
- EN 301 549 v3.2.1 (WCAG 2.1 AA) is the current EU requirement. Target WCAG 2.2 AA so the texts stay valid when a newer version applies.
- 1.4.1 Use of Color: never rely on colour alone. Every colour is paired with a cue that does not depend on colour (label, shape, position, order). This also covers colour blindness.

## Sources

- Library: Enhetsbibliotek (Figma `JmsgorAqvglqAzctc2uKVT`). Read-only; never modify.
- Output: Equipment captions (Figma `vOsrrAexH2tM2FYMI9X6jF`), component `Image caption`, one page per category.
- Facts come only from the image, Telenor.no help pages or the product team. Never invent facts. Models derived from set IDs are flagged for confirmation.

## Workflow

1. Look at the image first. Describe what is actually visible.
2. Write the caption (what it is and what it means), then the alt text.
3. Add open questions to the table, never to the caption.
4. Check against the QA list below.

## Caption and alt text rules

- Describe function and meaning. No instructions ("koble til", "trykk") in captions.
- Alt text is for blind, low-vision and screen reader users (WCAG 1.1.1; Digdir/Uutilsynet: alt text describes the motif, the visible caption adds purpose). Write 2-4 plain sentences, about 120-350 characters, in this order: what the image shows and the view; shape, colour and material; then the parts in fixed order (top to bottom or left to right) with colour AND position, and the text printed on ports, buttons and lamps. Start with "Dette bildet viser ..." (house style). Do not repeat the caption's explanation of what a part is for, and do not instruct. Say "to be confirmed" in the Avklaring column, never in the alt text.
- Alt text describes only what is visible. If a model name, port function or on/off state is not certain, flag it in Avklaring.
- Sets: write alt text per image, not per set. Close-ups say which part of the product they show and what surrounds it (neighbouring ports), so the user can place them.
- Caption is 1–2 sentences and adds meaning that alt text does not.
- Colours: always name the colour and a colour-independent cue, e.g. "Den nederste porten er blå og merket WAN."
- Text printed on ports, lamps and buttons is often small and hard to read. Explain it in the caption, e.g. "Porten merket PWR er strøminngangen." Mark the reading for fact-check in the Avklaring column.
- Router: LAN ports connect many kinds of equipment. The WAN port is the blue internet input.
- Cables: say what the cable connects, connector shape and colour with a cue, and no instructions.
- Wall sockets and adapters: name each port by its printed label.
- Off/on images that look identical get a neutral caption; the table notes it.
- Alt text length: 120-450 characters. Instructions (order, hold time, "at the same time") live in a separate instruction text, never in caption or alt text, because the same image can serve several instructions.
- Shape and position: for every highlighted button or port, state its shape (round, tall narrow pill, wide rounded rectangle, small flat) and its position relative to fixed landmarks (navigation ring with OK, power at the top, Telenor symbol at the bottom, neighbouring buttons or ports). This lets blind and low-vision users find the right control.
- Button combinations (pairing, sound selection, reset): the caption states only which buttons are marked and, if confirmed, what the pair is used for (e.g. "Hjem-knappen og OK-knappen. De to knappene brukes sammen når fjernkontrollen kobles til T-We-boksen"). Do not state a function for digit combinations, since digits serve many instructions. The alt text names each button, its shape and its position relative to the other.
- Supplier and model names: titles, captions and alt texts use Telenor's public product names only (WiFi Ruter 1, Fiberboks (ONT)); never Kaon, Zyxel, Nokia or Alcatel. Supplier and model codes live in the image ID. On the "forside" caption only, show the supplier and model as a small second line under the title (e.g. "Nokia G-010G-RQ", 14 px Light), so customers can match the label on the device. Illustration colour: do not describe the body colour of remotes and T-We boxes (illustrations differ from the physical product). Do state the body colour as "hvit" or "sort" (the words customers and agents use; not "lys", "mørk", "lysegrå" or "blå") for routers, amplifiers, ONTs and modems, so a white router is not mistaken for a black ONT. ONTs can be white or black. Illustration colours such as dark blue are only palette choices from Telegrafen, so never call a device blue. The text is also read aloud by customer agents on the phone, so use words that sound natural when spoken. Keep functional colours: yellow LAN, blue WAN or USB, lamp colours, the four colour buttons. Dim ("-dim") images: "Ingen knapper er markert", no colour.
- Product names: "WiFi Ruter 1/2/3" and "WiFi Forsterker 1/2/3" with digits in alt text and captions so screen readers say numbers (telenor.no help pages use Roman numerals; do not copy that). Router N pairs with amplifier N. T-We names: "T-We boks 2/3" and "T-We fjernkontroll 2/3". Technical IDs keep the hardware name (`zyxel-ruter-1`).
- Whenever a term or requirement is agreed in the session, update this file in the same turn.
- Write the skill and its rules in English; only the produced captions, alt text and examples are Norwegian Bokmål.
- Tone: du/vi, sentence case, no em dashes, no jargon without explanation.

## Button list pattern (Fjernkontrollknapper)

Applies to the category Fjernkontrollknapper only. Buttons are shown small in a list of `Funksjonskort` cards with image (96 px, no round background; the Infobox icon slot cannot be enlarged), button name as title, and one sentence explaining what the function does or means in use, not just its name (e.g. "Tar deg til startsiden, med anbefalinger, kanaler og appene dine"; lamps: what the colour means). No full stop, as for short labels in `telegrafen-ux-writing`. Styling: Color/Surface/Subtle, Color/Border/Default 1px, 20 padding, title 20 Medium, text 16 Light. List width 440 px as the Infobox standard; cards fill the container so they adapt to the screen. The text matches the overview page on Telenor.no, with new illustrations. Do not describe the image in the card text; the alt text in the table does that. The "see all functions" link is built in the implementation, not in Figma. Whether the images are decorative is unconfirmed; until confirmed, write alt text in the table and flag it in Avklaring.

## Data model

- Image ID = `<set>/<variant>`, for example `fjernkontroll-3/twe-home`. The ID links text to image; text is never stored in the image.
- Title pattern: `<Enhet>: <del>`.
- Table row: Bilde-ID, alt text, character count, status (`Utkast`), Avklaring (default "Faktasjekkes mot produktteam"). Keep these column names and values in Norwegian.
- Layout: one section per set, cells in a single horizontal row, no overlapping sections. One alt-text table per category page, outside the component.
- Intended implementation: a single source of truth in the asset bank / Gizmo with editing in one place only. Not yet decided.

## Example

Image: router seen from behind with a blue port labelled WAN.

- Good alt text: `Baksiden av en ruter med en blå WAN-port nederst.`
- Good caption: `Den nederste porten er blå og merket WAN. Det er her internett kommer inn.`
- Bad caption: `Koble kabelen til den blå porten.` (instruction, colour without a non-colour cue)

## QA checklist

- Caption matches the image.
- No instructions, no "må avklares" in caption text.
- Colour has a non-colour cue.
- Printed labels explained and flagged for fact-check.
- Alt text 120-450 characters, with shape and position for each highlighted control; no duplicate of caption.
- Open items are in Avklaring and status is `Utkast`.
- Sections do not overlap; nothing clipped (fresh screenshot).

## Handoff

State `Visual QA` and `WCAG 2.2 AA design review` results per `telegrafen-design-components`, list skipped or empty library sets, and name what needs fact-checking.
