# 5 ans après, nouvelle enquête sur les Panama Papers

Combien la base de données contient-elle de sociétés offshores différentes dont la source est "Panama Papers" ?
> SELECT count(*) from entity join source where source.source = 'Panama Papers'

Quel intermédiaire a créé le plus de sociétés offshores ? A-t-on son adresse et son pays ?
> 
