import csv
import json
import urllib.request
url = "https://github.com"
req = urllib.request.Request(url, headers={"User-Agent": "Mozilla/5.0"})
with urllib.request.urlopen(req) as response:
  data = response.read().decode("utf-8")
with open("api_data.csv", mode="w", newline="", encoding="utf-8") as f:
writer = csv.writer(f)
writer.writerow(["Fetched Data"])
writer.writerow([data])
print("CSVファイルの作成が完了しました。")
