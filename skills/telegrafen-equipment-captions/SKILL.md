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
- Supplier and model names: titles, captions and alt texts use Telenor's public product names only (WiFi Ruter 1, Fiberboks (ONT)); never Kaon, Zyxel, Nokia or Alcatel. Supplier and model codes live in the image ID. On the "forside" caption only, show the supplier and model as a small second line under the title (e.g. "Nokia G-010G-RQ", 14 px Light), so customers can match the label on the device. Longer explanations (what the lamps mean, what the port names mean) are not part of the caption or alt text. They go in the accordion that is part of the Image caption component ("Show details" property, Accordion Item "Utvidet forklaring" below the caption). Heading: a question that fits, e.g. "Hva betyr lampene og navnene?". Content structure, as in the ONT G-010G-RQ lamps cell (5:3572): first a sub-heading "Lampene på fiberboksen" (or "Lampene på modemet") with one line per name, name in bold followed by a colon ("**Power:** fiberboksen har strøm."; keep the colon so the name is separated from the explanation when read aloud), then one sub-heading per lamp with one line per state ("**Lyser grønt:** ...", "**Blinker grønt:** ...", "**Slukket:** ..."; state in bold with colon, like the names). Facts come from approved Telenor help pages and are flagged for fact-checking, never invented. Front vs close-up: the "forside" image gets a general description of the device (form, colour, main parts). The "forside" and "bakside" captions say concretely what you see and what each visible part is for (e.g. "Den grønne lampen øverst er for internett, og den hvite under er for strøm og WPS", plus the WPS-knapp, ports and their colours), but never how a part can light up or behave, and they never have an accordion. The close-ups (lamps, WPS-knapp, LAN-porter, WAN-port) show how a part can look or light up and what that means: the caption says what it is and that the way it lights or blinks tells something, and the accordion carries the longer explanation (lamp states, what WPS, LAN and WAN are). Front captions name every printed lamp or count them, and say what each is for, using the Telenor help pages as source (telenor.no/kundeservice/internett/modem-og-ruter/: wifi-ruter, wifi-ruter-2, wifi-forsterker-2, kaon-kabelmodem). Example from the help page: on WiFi-forsterker 2 the upper lamp shows coverage and the lower shows power. Back captions mention the reset hole where the help page names it. Amplifier lamp close-ups: caption says the amplifier has two lamps (upper = coverage, lower = power and WPS); accordion 'Hva betyr lampene?' with groups 'Øverste lampe: dekning' (green good, yellow OK, red weak, off not connected), 'Nederste lampe: strøm og WPS' (white steady power, blinking white starting, blinking green WPS, off no power) and 'Begge lampene' (blinking yellow = software update). Source: Telenor.no WiFi Forsterker II. Accordion only for longer explanations: do not hide a short text (about one or two sentences) in an accordion, because it forces the user to click to read one sentence. Put short explanations, such as what POE means, openly in the caption. Use an accordion only when the explanation has several parts, such as lamp states. Modem and ONT: the modem's WAN port and the ONT's network (LAN/GE/ETHERNET) port send internet on to the router; they do not receive it. The modem receives internet through the coaxial cable (CABLE IN), the ONT through the fibre. WAN port on routers: "WAN-porten er blå og merket WAN. Den er ruterens inngang for internett fra fiberboks, modem eller trådløs bredbånd antenne." Never mention veggkontakt for the WAN port; the same sources apply to the cable caption and the accordion. ONT lamp close-ups: the caption states the normal state in one sentence ("Lampene på fiberboksen lyser stabilt grønt når alt er ok. Alarm-lampen er da slukket."), and the accordion "Hva betyr lampene?" lists every printed lamp name as on that model (e.g. Power, Optical, Alarm, LAN, Update, Video on the G-011G-P; Power, Alarm, Connection, ETH on the G-010G-P), name in bold with a colon, then a group "Når alt er ok". Lamp names and states differ per box, so facts come from Telenor.no or the product team per model; mark unknown meanings "[avklar med produktteamet]". Apply this the same way for routers, amplifiers, ONTs and modems; where no approved facts exist, leave the accordion out and flag it in Avklaring. A close-up describes only what is zoomed in, with shape and printed text, and does not describe neighbouring parts outside the crop. For lamp close-ups, zoom in (clone the image at 3x in a temporary frame) and read every printed label, then list each lamp with its label and colour in order. Illustration colour: do not describe the body colour of remotes and T-We boxes (illustrations differ from the physical product). Do state the body colour as "hvit" or "sort" (the words customers and agents use; not "lys", "mørk", "lysegrå" or "blå") for routers, amplifiers, ONTs and modems, so a white router is not mistaken for a black ONT. ONTs can be white or black. Illustration colours such as dark blue are only palette choices from Telegrafen, so never call a device blue. The text is also read aloud by customer agents on the phone, so use words that sound natural when spoken. Keep functional colours: yellow LAN, blue WAN or USB, lamp colours, the four colour buttons. Dim ("-dim") images: "Ingen knapper er markert", no colour.
- Product names: "WiFi Ruter 1/2/3" and "WiFi Forsterker 1/2/3" with digits in alt text and captions so screen readers say numbers (telenor.no help pages use Roman numerals; do not copy that). Router N pairs with amplifier N. T-We names: "T-We boks 2/3" and "T-We fjernkontroll 2/3". Technical IDs keep the hardware name (`zyxel-ruter-1`).
- Whenever a term or requirement is agreed in the session, update this file in the same turn.
- Write the skill and its rules in English; only the produced captions, alt text and examples are Norwegian Bokmål.
- Tone: du/vi, sentence case, no em dashes, no jargon without explanation.

## Button list pattern (Fjernkontrollknapper)

Applies to the category Fjernkontrollknapper only. Buttons are shown small in a list of `Funksjonskort` cards with image (96 px, no round background; the Infobox icon slot cannot be enlarged), button name as title, and one sentence explaining what the function does or means in use, not just its name (e.g. "Tar deg til startsiden, med anbefalinger, kanaler og appene dine"; lamps: what the colour means). No full stop, as for short labels in `telegrafen-ux-writing`. Styling: Color/Surface/Subtle, Color/Border/Default 1px, 20 padding, title 20 Medium, text 16 Light. List width 440 px as the Infobox standard; cards fill the container so they adapt to the screen. The text matches the overview page on Telenor.no, with new illustrations. Do not describe the image in the card text; the alt text in the table does that. The "see all functions" link is built in the implementation, not in Figma. Whether the images are decorative is unconfirmed; until confirmed, write alt text in the table and flag it in Avklaring.

## Data model

- Image ID = `<set>/<variant>`, for example `fjernkontroll-3/twe-home`. The ID links text to image; text is never stored in the image.
- Title pattern: `<Enhet>: <del>`, where `<Enhet>` is always the full public name with number, on every image of the set including close-ups: `WiFi Ruter 3: forsiden`, `WiFi Ruter 3: lamper`, `WiFi-forsterker 2: WPS-knapp`. Never only "Ruter", "Ruter 3" or "Forsterker". Our routers are called WiFi Ruter 1, 2 and 3. The same applies to the first mention in a caption ("WiFi Ruter 3 sett forfra"); later the generic word "ruteren" is fine.
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
