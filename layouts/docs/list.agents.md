# Reef Docs Agent Export

This route aggregates the raw markdown source for the Reef docs site.
Use the file path and page URL for mapping changes back to the repo.
Each fenced `md` block preserves the source file contents for that document.

{{ $allFiles := partial "main/docs-agent-files.html" (dict "dir" "content/docs" "base" "docs") -}}
{{ $docsIndex := partial "main/docs-agent-entry-data.html" (dict "site" .Site "path" "docs/_index.md") -}}

## Docs Index

{{ partial "main/docs-agent-entry.md" (dict "entry" $docsIndex) -}}
{{ range sort .Site.Menus.docs "Weight" -}}
  {{ if gt (len (findRE "^/docs/[^/]+/$" .URL)) 0 -}}
  {{ $sectionIndexPath := printf "docs/%s/_index.md" .Identifier -}}
  {{ if in $allFiles $sectionIndexPath -}}
  {{ $sectionIndex := partial "main/docs-agent-entry-data.html" (dict "site" $.Site "path" $sectionIndexPath) -}}
## {{ .Name }}

{{ partial "main/docs-agent-entry.md" (dict "entry" $sectionIndex) -}}
  {{ end -}}
  {{ $sectionPrefix := printf "docs/%s/" .Identifier -}}
  {{ $entries := slice -}}
  {{ range $allFiles -}}
    {{ if and (hasPrefix . $sectionPrefix) (ne . $sectionIndexPath) -}}
      {{ $entries = $entries | append (partial "main/docs-agent-entry-data.html" (dict "site" $.Site "path" .)) -}}
    {{ end -}}
  {{ end -}}
  {{ range sort $entries "sortKey" -}}
{{ partial "main/docs-agent-entry.md" (dict "entry" .) -}}
  {{ end -}}
  {{ end -}}
{{ end -}}
