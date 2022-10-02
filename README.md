# pycdmsapi

Our first implementation of OpenCDMS API ([opencdms-api](https://github.com/opencdms/opencdms-api)) was a FastAPI application that [mounted existing WSGI applications](https://fastapi.tiangolo.com/advanced/wsgi/) to expose APIs served by:
- [geopython/pygeoapi](https://github.com/geopython/pygeoapi) (flask)
- [opencmds/surface](https://github.com/opencdms/surface) (django)
- [opencdms/MCH-API](https://github.com/opencdms/mch-api) (flask)
- [opencdms/Climsoft-API](https://github.com/opencdms/climsoft-api) (FastAPI).

Instead of providing different APIs for each CDMS, our next version will provide a *single shared/common API* that resembles the WMO Climate Data Model (CDM) standard and is not specific to particular CDMS. This new version will also make use of pygeoapi to provide the OGC API standards implemented by pygeoapi (including [OGC API - EDR](https://www.ogc.org/standards/ogcapi-edr)).

We're intending to develop a single application that provides support for the OCG API standards and CDMS-specific capabilities using a single framework-agnostic server application. To achieve this we will follow the approach taken by pygeoapi which does not import dependencies from any particular Python web framework.
