from zipfile import ZipFile
from pathlib import Path

# Prepare the LICENSE.html content
license_html_content = """
<!DOCTYPE html>
<html lang="en">
<head><meta charset="UTF-8"><title>Thinker V1 License</title></head>
<body>
  <h2>Proprietary License – Thinker V1</h2>
  <p><strong>Author:</strong> Zubin Qayam<br>
     <strong>Email:</strong> <a href="mailto:zubin@autotechserv.com">zubin@autotechserv.com</a><br>
     <strong>Date:</strong> July 25, 2025</p>
  <p>This software (Thinker V1) is an independent research module under development, created by Zubin Qayam as part of the AutoserGPT AI Workstation roadmap.</p>
  <p><strong>Rights:</strong> All rights are reserved. No copying, redistribution, or reuse is allowed without explicit permission.</p>
  <p>Approved use cases and integration requests must be routed through the original author.</p>
</body>
</html>
"""

# Define the output directory and file paths
output_dir = Path("/mnt/data/thinker_license")
output_dir.mkdir(parents=True, exist_ok=True)
license_file = output_dir / "LICENSE.html"

# Write the LICENSE.html file
with open(license_file, "w") as f:
    f.write(license_html_content)

# Create a zip file containing the LICENSE.html
zip_path = Path("/mnt/data/ThinkerV1_License.zip")
with ZipFile(zip_path, "w") as zipf:
    zipf.write(license_file, arcname="LICENSE.html")

zip_path.name