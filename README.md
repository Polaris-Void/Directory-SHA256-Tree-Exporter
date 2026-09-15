<p align="right">
  <a href="README_FA.md"> <strong>فارسی</strong></a>
</p>

---

# Directory Tree, Metadata & SHA-256 Auditor

A high-precision, automated Windows Batch & PowerShell hybrid utility designed to recursively scan directory structures, map visual folder hierarchies, extract file metadata, and calculate cryptographic **SHA-256 hashes** for comprehensive data integrity auditing.

It outputs an organized, wide-format UTF-8 report without requiring third-party tools, external libraries, or administrator privileges.

---

## ✨ Features

- **🔒 Cryptographic SHA-256 Hashing:** Generates a unique 64-character SHA-256 checksum for every file via native PowerShell (`Get-FileHash`) to verify data integrity and detect tampering or corruption.
- **🛡️ Error Resilient (Access Denied Handling):** Gracefully catches locked or restricted files and tags them as `<ACCESS DENIED>` without halting the scan.
- **🌳 Visual Directory Hierarchy:** Renders folder structures with clean Unicode box-drawing characters (`├──`, `└──`, `│`) for clear structural visualization.
- **📊 Detailed File Metadata:** Captures human-readable file sizes (formatted dynamically to B, KB, MB, or GB), exact modification dates, and creation dates.
- **📐 Dynamic Wide-Table Formatting:** Measures path lengths and automatically aligns columns and table borders to comfortably accommodate deep folder paths and 64-character hashes.
- **📈 Statistical Summary:** Provides an audit summary displaying total folders scanned, total files processed, aggregate size (both human-readable and raw bytes), and execution time using high-precision timers.
- **🌐 Full UTF-8 Encoding:** Accurately preserves international filenames, Persian/Arabic characters, special symbols, and emojis without encoding errors.
- **🛡️ Self-Excluding Log:** Automatically ignores its own log file (`File List Log.txt`) during scanning to prevent skewed audit numbers.
- **⚡ Zero Dependencies:** 100% native Windows script using Command Prompt and PowerShell.

---

## 📄 Output Preview

The generated `File List Log.txt` creates an organized tabular report similar to this:

```text
=================================================================================================================================================================
                                                                DIRECTORY TREE & FILE AUDIT REPORT                                                               
=================================================================================================================================================================
  Target Path  :  C:\MyProject
  Generated On :  2026-09-15 16:00:00
=================================================================================================================================================================

  PATH / TREE STRUCTURE                   SIZE         DATE MODIFIED          DATE CREATED                            SHA-256 HASH                          
  ---------------------------------   ----------   -------------------   -------------------   ----------------------------------------------------------------
  .                                       <DIR>    2026-09-15 15:30:10   2026-09-15 15:30:10   -                                                               
  ├── src/                                <DIR>    2026-09-15 15:45:22   2026-09-15 15:30:15   -                                                               
  │   ├── index.js                     12.45 KB    2026-09-15 15:44:00   2026-09-15 15:31:00   A1B2C3D4E5F60718293A4B5C6D7E8F90123456789ABCDEF0123456789ABCDEF0
  │   └── utils.js                      4.10 KB    2026-09-15 15:40:12   2026-09-15 15:31:20   E3B0C44298FC1C149AFBF4C8996FB92427AE41E4649B934CA495991B7852B855
  └── README.md                         1.85 KB    2026-09-15 15:50:00   2026-09-15 15:30:10   8F434346648F6B96DF89DDAE13A4C7F7AB190A97A0DF161A92804CFD363D52A0
  ---------------------------------   ----------   -------------------   -------------------   ----------------------------------------------------------------

=================================================================================================================================================================
                                                                       STATISTICAL SUMMARY                                                                       
=================================================================================================================================================================
  Total Folders   :  1
  Total Files     :  3
  Total File Size :  18.40 KB (18,842 Bytes)
  Execution Time  :  0.42 Seconds
=================================================================================================================================================================
```

---

## 🚀 How to Use

1. Place the script file (saved with a `.bat` extension, e.g., `Export-File-List-SHA256.bat`) inside the directory you want to audit.
2. **Double-click** the script to execute it.
3. The terminal will display real-time scan progress and statistics.
4. A report file named **`File List Log.txt`** will be generated in the same directory.
5. The console window will automatically close after 5 seconds (or upon pressing any key).

---

## 💻 System Requirements

- **OS:** Windows 8.1, Windows 10, or Windows 11.
- **PowerShell:** Version 4.0 or later (required for `Get-FileHash`; enabled by default on Windows 8.1, 10, and 11).
- **Permissions:** Standard user privileges (Administrator access is **not** required unless scanning protected system folders).
