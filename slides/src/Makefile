LECNO = 0
FLAGS = --scripts https://cdn.tonycrane.cc/heti/heti.js,heti_worker.js --template template.html

.PHONY: live build all clean live-home build-home

live:
	@echo "Previewing lec$(LECNO) slides..."
	-@reveal-md lec$(LECNO).md -w $(FLAGS) || true

build:
	@echo "Building lec$(LECNO) slides..."
	@reveal-md lec$(LECNO).md $(FLAGS) --static ../site/lec$(LECNO) --assets-dir assets
	@rm ../site/lec$(LECNO)/lec$(LECNO).html

live-home:
	@echo "Previewing home slides..."
	-@reveal-md home.md -w $(FLAGS) || true

build-home:
	@echo "Building home slides..."
	@reveal-md home.md $(FLAGS) --static ../site --assets-dir assets
	@rm ../site/home.html

all:
	@echo "Building all slides..."
	@make build-home
	@for i in `seq 0 6`; do \
		make LECNO=$$i build; \
	done

clean:
	@echo "Cleaning up..."
	rm -rf ../site/
