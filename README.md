# run

A lightweight Bash script to launch GUI applications from the terminal. It handles process detachment, output silencing, and automatic terminal closure.

## Features

* **Default:** Launches app, silences output, and immediately closes the terminal window.
* **Sticky (`-s`):** Launches app silently but keeps the terminal open.
* **Debug (`-sd`):** Launches app, keeps terminal open, and shows stdout/stderr.

## Installation

1. Create the executable file in your local binary path:

```bash
mkdir -p ~/.local/bin
nano ~/.local/bin/run

```

2. Paste the script content (see below) into the file and save.
3. Make the script executable:

```bash
chmod +x ~/.local/bin/run

```

4. Ensure `~/.local/bin` is in your `$PATH`.

## Usage

**Syntax:** `run [flags] <application> [args]`

| Flag | Behavior | Terminal State | Output |
| --- | --- | --- | --- |
| **(None)** | Default | **Closed** (Kills parent process) | Silenced |
| **-s** | Sticky | **Open** | Silenced |
| **-sd** | Sticky Debug | **Open** | Visible |

### Examples

**Launch Browser and Close Terminal:**

```bash
run helium-browser

```

**Launch File Manager and Keep Terminal Open:**

```bash
run -s thunar

```

**Launch App with Debug Logs:**

```bash
run -sd code .

```
