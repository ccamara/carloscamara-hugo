+++
# Custom widget.
# An example of using the custom widget to create your own homepage section.
# To create more sections, duplicate this file and edit the values below as desired.
widget = "custom-search"
active = false
date = "2016-04-20T00:00:00"

# Note: a full width section format can be enabled by commenting out the `title` and `subtitle` with a `#`.
title = "Búsqueda"
subtitle = ""

# Order that this section will appear in.
weight = 70

+++

<!-- <iframe src="https://duckduckgo.com/search.html?site=carloscamara.es" style="overflow:hidden;margin:0;padding:0;width:408px;height:40px;" frameborder="0"></iframe> -->

<form method="get" id="search" action="http://duckduckgo.com/">
  <input type="hidden" name="sites" value="carloscamara.es"/>
  <input type="hidden" name="k9" value="#FF8000"/>
  <input type="hidden" name="kt" value="Merriweather"/>
  <input type="text" name="q" maxlength="255" placeholder="Buscar&hellip;"/>
  <input type="submit" value="DuckDuckGo Search" style="visibility: hidden;" />
</form>

Esta web no tiene buscador interno, sino que utiliza un buscador externo que muestra únicamente los resultados de este sitio, así que no te sorprendas cuando seas redirigido a otra web al hacer hacer clic en la tecla intro para buscar.

Como valoro mucho tu privacidad, ese buscador externo es [duckduckgo](http://duckduckgo.com), que no almacena ningún tipo de dato tuyo como hacen otros buscadores famosos, [aquí tienes una explicación de los motivos](https://duckduckgo.com/privacy).
