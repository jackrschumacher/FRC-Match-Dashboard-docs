---
title: Endpoints
weight: 3
description: "FRC Dashboard endpoints"
---

## Active match info

### Read APIs

#### Active Match

*Provides alliance team numbers, individual EPAs, live scores, and predicted alliance total EPAs.*

```
http://[device-ip]:5000/api/active_match.json
```

#### Single team 

```
http://[device-ip]/api/team.json
```

#### Head to head

```
http://[device-ip]:5000/api/h2h.json
```

#### Rankings

```
http://[device-ip]:5000/api/rankings.json
```

### Edit APIs
{{< details title="Editing methods (example)" closed="true" >}}

**Using inbuilt API methods:**

```powershell
# Edit a team's record and EPA
Invoke-RestMethod -Uri http://localhost:5000/api/edit/team -Method Post -ContentType "application/json" -Body '{"team_key":"frc1732","updates":{"wlt":"6-1-0","epa":45.2}}'

# Rename a match
Invoke-RestMethod -Uri http://localhost:5000/api/edit/match_title -Method Post -ContentType "application/json" -Body '{"match_key":"2026mroc_qm12","title":"Finals Rematch"}'

# Swap a match's teams
Invoke-RestMethod -Uri http://localhost:5000/api/edit/match_roster -Method Post -ContentType "application/json" -Body '{"match_key":"2026mroc_qm12","red_keys":["1732","930","590"],"blue_keys":["254","1114","118"]}'
```

**Using curl:**

```shell
curl -X POST http://localhost:5000/api/edit/team \
  -H "Content-Type: application/json" \
  -d '{"team_key":"frc1732","updates":{"wlt":"6-1-0","epa":45.2}}'
```



{{< /details >}}

#### Edit team 

```
http://[device-ip]:5000/api/edit/team
```

{{< details title="Example edit" closed="true" >}}
Overriding team fields
```json
{
  "team_key": "frc1732",
  "updates": { "epa": 45.2, "wlt": "6-1-0", "notes": "strong auto" }
}
```
{{< /details >}}

#### Edit match title
```
http://[device-ip]:5000/api/edit/match_title
```
{{< details title="Example edit" closed="true" >}}
Overriding match fields
```json
{ "match_key": "2026mroc_qm12", "title": "Finals Rematch" }
```
{{< /details >}}


#### Edit match roster
```
http://[device-ip]:5000/api/edit/match_roster
```
{{< details title="Example edit" closed="true" >}}
Overriding match roster fields
```json
{
  "match_key": "2026mroc_qm12",
  "red_keys":  ["1732", "930", "590"],
  "blue_keys": ["254", "1114", "118"]
}
```
{{< /details >}}