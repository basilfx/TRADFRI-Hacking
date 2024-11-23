PROJECT := Devboard

KICAD_CLI := kicad-cli
TRACESPACE_CLI := npx @tracespace/cli

all: schema board

schema:
	$(KICAD_CLI) sch export pdf --output "$(PROJECT).pdf" "$(PROJECT).kicad_sch"

board:
	mkdir -p "build"
	mkdir -p "images"
	$(KICAD_CLI) pcb export gerbers --output "build" --layers "F.Cu,B.Cu,F.Paste,B.Paste,F.SilkS,B.SilkS,F.Mask,B.Mask,Edge.Cuts"  "$(PROJECT).kicad_pcb"
	$(KICAD_CLI) pcb export drill --output "build" "$(PROJECT).kicad_pcb"
	$(TRACESPACE_CLI) --noLayer --out "build" "build/*"
	cp "build/$(PROJECT).top.svg" "images/$(PROJECT)_Top.svg"
	cp "build/$(PROJECT).bottom.svg" "images/$(PROJECT)_Bottom.svg"

clean:
	rm -rf "build"

.PHONY: all clean
