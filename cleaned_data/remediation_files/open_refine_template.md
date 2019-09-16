# OpenRefine Template for Alumnus Remediation

---

## Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```

## Row Template

```
<mods>
<identifier type="issn">1521-6411</identifier>
<identifier type="pid">{{cells['PID'].value}}</identifier>
<identifier type="filename">{{cells['filename'].value}}</identifier>
{{if(isBlank(cells['title'].value), '', '<titleInfo supplied="yes"><title>' + cells['title'].value + '</title></titleInfo>')}}
{{if(isBlank(cells["abstract"].value),'', '<abstract>' + cells['abstract'].value + '</abstract>')}}
{{'<originInfo>' + if(isBlank(cells['year'].value), '', '<dateIssued>' + cells['year'].value + '</dateIssued>') + if(isBlank(cells['dateIssued_edtf'].value), '', '<dateIssued encoding="edtf" keyDate="yes">' + cells['dateIssued_edtf'].value + '</dateIssued>') + '<publisher>' + cells['publisher'].value + '</publisher><place><placeTerm valueURI="http://id.loc.gov/authorities/names/n79109786">' + cells['placeTerm'].value + '</placeTerm></place><issuance>serial</issuance></originInfo>'}}
<physicalDescription><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form></physicalDescription>
{{if(isBlank(cells['DPN_note'].value), '', '<note displayLabel="dpn">' + cells['DPN_note'].value + '</note>')}}
{{if(isBlank(cells['subject'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject_URI'].value + '"><topic>' + cells['subject'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject2'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject2_URI'].value + '"><topic>' + cells['subject2'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject3'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject3_URI'].value + '"><topic>' + cells['subject3'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_name'].value), '', '<subject authority="naf" valueURI="' + cells['subject_name_URI'].value + '"><name><namePart>' + cells['subject_name'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_geo'].value), '', '<subject><geographic authority="naf" valueURI="' + cells['subject_geo_URI'].value + '">' + cells['subject_geo'].value + '</geographic><cartographics><coordinates>' + cells['coordinates'].value + '</coordinates></cartographics></subject>')}}
<language><languageTerm type="text" authority="iso639-2b">English</languageTerm></language>
<typeOfResource>text</typeOfResource>
<classification authority="lcc">{{cells['classification'].value}}</classification>
<relatedItem displayLabel="Project" type="host"><titleInfo><title>{{cells['digital_collection'].value}}</title></titleInfo></relatedItem>
<location><physicalLocation valueURI="http://id.loc.gov/authorities/names/no2014027633">University of Tennessee, Knoxville. Special Collections</physicalLocation></location>
<recordInfo><recordContentSource valueURI="http://id.loc.gov/authorities/names/n87808088">University of Tennessee, Knoxville. Libraries</recordContentSource><recordOrigin>Created and edited in general conformance to MODS Guidelines (Version 3.5).</recordOrigin></recordInfo>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>
```

## Row Separator

**LEAVE BLANK**

## Suffix

```
</modsCollection>
```