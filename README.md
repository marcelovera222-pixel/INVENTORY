# Mr. Lukas LLC Inventory Website

This local inventory website supports separate inventory views for Dallas and Mission. The current PDF-backed inventory is loaded as Dallas.

## What it does

- Shows the imported inventory with starting and current quantities.
- Switches between Dallas and Mission inventories.
- Uploads invoices to subtract inventory.
- Uploads landing bills to add inventory.
- Lets you manually add, subtract, or set stock counts without uploading a file.
- Supports a private staff access code for hosted use.
- Reads PDF, CSV, Excel, and text files.
- Shows every matched line for review before changing inventory.
- Saves inventory and movement history in the `data` folder.
- Exports the current inventory to CSV.
- Includes a dashboard, document intake screen, inventory catalog, and activity history.

## Run It

For a quick local test on this computer, use the bundled Python runtime from Codex.

Use the bundled Python runtime from Codex:

```bash
/Users/marcelochello24/.cache/codex-runtimes/codex-primary-runtime/dependencies/python/bin/python3 scripts/import_inventory.py --location dallas
/Users/marcelochello24/.cache/codex-runtimes/codex-primary-runtime/dependencies/python/bin/python3 server.py
```

Then open:

```text
http://127.0.0.1:8765
```

## Put It Online

To use the inventory from different cities and different devices, deploy it as a hosted website instead of using the local address above. See `DEPLOYMENT.md`.

The hosted setup writes inventory changes to a persistent data folder so Dallas and Mission inventory updates are not lost when the website restarts.

Set `INVENTORY_STAFF_CODE` in the hosted service to require an access code before staff can open the inventory.

## Important

Uploaded documents can have different layouts. The program matches known SKUs and suggests quantities, but you should review the lines before applying them, especially when a SKU appears on more than one product.
