INPUT=./resume.md
OUTPUT=JoshSurberResume
STYLE=./github.css

OUTPUT_HTML=index.html
# OUTPUT_HTML=$(OUTPUT).html
OUTPUT_PDF=$(OUTPUT).pdf
OUTPUT_DOCX=$(OUTPUT).docx
OUTPUT_RTF=$(OUTPUT).rtf

all: html pdf docx rtf

pdf: init
	pandoc $(INPUT) \
	--standalone \
	--from=markdown \
	--to=html \
	--output=$(OUTPUT_PDF) \
	--pdf-engine=wkhtmltopdf \
	--css=$(STYLE) \
	--metadata=margin-left:0 \
	--metadata=margin-right:0 \
	--metadata=margin-top:0 \
	--metadata=margin-bottom:0

html: init
	pandoc $(INPUT) \
	--standalone \
	--from=markdown --to=html \
	--css=$(STYLE) \
	--output=$(OUTPUT_HTML)

docx: init
	pandoc $(INPUT) \
	--standalone \
	--from=markdown --to=docx \
	--output=$(OUTPUT_DOCX)
	# --reference-doc=$(STYLES)/reference.docx \

rtf: init
	pandoc $(INPUT) \
	--standalone \
	--from=markdown --to=rtf \
	--output=$(OUTPUT_RTF)

init:

clean:
	rm -f $(OUTPUT_RTF)
	rm -f $(OUTPUT_HTML)
	rm -f $(OUTPUT_DOCX)
	rm -f $(OUTPUT_PDF)
