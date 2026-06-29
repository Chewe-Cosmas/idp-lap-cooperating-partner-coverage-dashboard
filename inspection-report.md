# GeoPackage inspection report

Source: IDP Cooperating Partner Coverage Dataset.gpkg  
Inspected: 29 June 2026

## Contents

| Layer | Geometry | CRS | Features | Purpose |
|---|---|---:|---:|---|
| Confirmed_Districts | MultiPolygon | EPSG:32736 | 14 | Confirmed partner-supported districts |
| District_Under_Consideration | MultiPolygon | EPSG:32736 | 7 | Prospective district coverage |
| Districts_Boundaries | MultiPolygon | EPSG:32736 | 116 | District reference boundaries |
| Province_Commitment | MultiPolygon | EPSG:32736 | 4 | Province-level review commitments |
| Provinces_Boundary | MultiPolygon | EPSG:4326 | 10 | Province reference boundaries |
| layer_styles | Attributes | — | — | QGIS styling metadata |

## Coverage summary

There are 14 spatially confirmed districts, 7 districts under consideration, and 4 province commitments. Partners are GIZ, UNICEF, WWF, Global Green Growth Institute, International Crane Foundation, and TRALARD. TRALARD is represented as a non-spatial broad commitment covering 27 districts (exact district list TBD). Projects are IDP, LAP, and IDP Review.

Confirmed district coverage occurs in Central, Luapula, North-Western and Southern. Prospective coverage occurs in Central, Southern and Western. Province commitments are recorded for Central, Copperbelt, Eastern and Southern.

## Data observations

- PovName appears to be a misspelling of ProvName.
- Province_Commitment.Status contains both Province Commitment and the misspelled Province Commiment. The dashboard preserves the source wording.
- Itezhi-Tezhi has ProvNo 101 but PovName Southern. This possible coding inconsistency should be reviewed.
- Mumbwa appears as confirmed for GIZ and under consideration for WWF; both records are retained and the map identify result follows the active status filter.
- TRALARD has no verified district geometries in the source and therefore creates no map highlight.
- Geometry was transformed from UTM Zone 36S to WGS84 and simplified to about 0.0012 degrees for responsive web display. Attributes were preserved.

## Dashboard

The offline dashboard provides partner, project, province, text and status filters; layer visibility; pan and zoom; feature tooltips; partner totals; and a synchronized coverage register.