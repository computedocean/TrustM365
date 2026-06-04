# TrustM365 Sentinel Content Pack

This folder contains reusable artifacts for Microsoft Sentinel:

- analytics-rules/: Scheduled rule templates for drift and remediation incidents.
- workbooks/: Workbook definitions for monthly drift telemetry.
- ../kql/: KQL query library for SOC tuning and hunting.

## Deployment Inputs

You need:

- Azure subscription ID
- Resource group name
- Log Analytics workspace name
- Sentinel enabled on the workspace

## Quick Deploy (PowerShell)

Use the deployment helper script:

```powershell
scripts/sentinel/deploy/deploy_content_pack.ps1 -SubscriptionId <subId> -ResourceGroup <rg> -WorkspaceName <workspace> -TablePrefix TrustM365
```

Then import workbook JSON manually from:

- data/sentinel/workbooks/TrustM365-Drift-Monthly.workbook.json

## Validation

Use the validation script before deployment:

```bash
node scripts/sentinel/validate/validate_sentinel_assets.js
```

The validator checks that required files and JSON assets are present and parse correctly.
