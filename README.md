# pdf-parse-form

Branched from https://gitlab.com/autokent/pdf-parse which seems to be abandoned.

Added an updated pdfjs v2.15.349 in lib\pdf.js
Updated pdf-parse.js to use this version
(note dommatrix and web-streams-polyfill are needed to run quickstart.js)
A demo form OoPdfFormExample is in tests\data from http://foersom.com/org/HowTo/OoCreatePdfForm.html

Added source:
		if (ret.info.IsAcroFormPresent) {
			let formData = await doc.getFieldObjects().catch(function(err) {
			return err;
			});
			ret.formData = formData ? formData : null;
		};

When included in N8N https://n8n.io/ the readpdf node will also read form data into theJSON struct
https://docs.n8n.io/integrations/core-nodes/n8n-nodes-base.readpdf/


## License
[MIT licensed](https://gitlab.com/autokent/pdf-parse/blob/master/LICENSE) and all it's dependencies are MIT or BSD licensed.
