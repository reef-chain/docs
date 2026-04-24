{{- $entry := .entry -}}
### {{ $entry.title }}

File: `{{ $entry.path }}`
URL: {{ $entry.url }}

~~~~md
{{ $entry.source }}
~~~~

{{ if eq $entry.url "(not published as a standalone page)" }}
Note: this markdown file lives in the repo but does not generate its own public page.

{{ end }}
