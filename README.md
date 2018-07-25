# KMDCoinSupply
<br>
# Bash to export the history
<br><br>
#!/bin/bash<br>
for i in {0..936039}<br>
do<br>
   ./komodo-cli coinsupply $i >> fundsexport.json<br>
echo "," >> fundsexport.json<br>
done<br>
<br><br><br>


# Python To Export:

import json<br>
import csv<br>
<br><br>
with open('fundsexport.json', 'r') as f:<br>
    dicts = json.load(f)<br>
out = open('fundsexport.csv', 'w')<br>
writer = csv.DictWriter(out, dicts[0].keys())<br>
writer.writeheader()<br>
writer.writerows(dicts)<br>
out.close()<br>
