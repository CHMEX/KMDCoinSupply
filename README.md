# KMDCoinSupply

# Bash to export the history

#!/bin/bash
for i in {0..936039}
do
   ./komodo-cli coinsupply $i >> fundsexport.json
echo "," >> fundsexport.json
done



# Python To Export:

import json
import csv

with open('fundsexport.json', 'r') as f:
    dicts = json.load(f)
out = open('fundsexport.csv', 'w')
writer = csv.DictWriter(out, dicts[0].keys())
writer.writeheader()
writer.writerows(dicts)
out.close()
