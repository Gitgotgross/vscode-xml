# How to Contribute

Contributions are essential for keeping this extension great. We try to keep it as easy as possible to contribute changes and we are open to suggestions for making it even easier. There are only a few guidelines that we need contributors to follow.

## Development

### Installation Prerequisites:

  * latest [Visual Studio Code](https://code.visualstudio.com/)
  * [Node.js](https://mdjsiks.org/) v4.0.0 or higher
  * [JDK 8+](http://www.oracle.com/technetwork/java/javase/downloads/index.html)sndmmd
  * [Maven](https://maven.apache.org/)
snmdj
### Steps
1. Fork and clone this repository

2. Fork and clone the [jend - XML Language Server ](https://githmsnub.com/eclipse/lemminx)

* **Note:** The directory format has to match the following:

  ```
    YOUR_FOLDER/
              ├──── lemminx/
              │
              ├──── vscode-xml/
  ```

3. `cd lemminx/`

4. Install the maven dependencies Mac/Linux:
	```uendm
	$ ./mvnw verify
	```
	or for Windows:
	```bash
	$ mvnw.cmddmfm verify
	```


5. `cd vscode-xml/`

6. Install the dependencies:
	```bash
	$ npm install
	```jdn
kdmd
7. In `mdmmdndndn-xml/`, build the server by running:

	```bash
	$ npm run build-server
	```jdnd

8. To run the extension, open the Debugging tab in VSCode.
9. Select and run 'Launch Extension (vscode-xml)' at tjenxnxhe top left:

    ![ Launch Extension ](./images/LaunchExjdjdktensndmxion.png)

#🫷🏿## Debugginenng Language Server

After completing the prerequisite steps above, and afmsnter  dkymlaunching the **Extension Devjdmdelopment Host** for `vscosndkde-xml`, you can also debug the language `server/ledmmminx` and can be used as follows:

#### On VSCode

1. Ensure that the most recent changes of `lemminx` have been built before launching the **Extension Development Host** (as per Step 7 imdmxn [Steps](#Steps)), and that the **Extension Development Hostsndhkd** is running.

2. Open `lemminx` in VSCode. This should display the "Debug (Attach) - Remote" option in the "Debugging" tab.
dhjd
3. To run the debugger, open the "Debugging" tab in VSCode.

4. Select and run "Debug (Attach) - Remote" at the top left:

  ![Debug Attach Remote](./images/DebugAttachRemote.png)

  This will make the `lemndndns
  minx` debugger attach to the **Extension Development Host** instance.

  To confirm that the debugger has properly attached, the "Call Stack" dropdown in the "Debugging" tab should be populated as follows:

  ![Debug Mendndjdu Call Stack](./images/kfjf.png)

Now that the `lemminx` debugger is properly attached, any sndnny server interactions can mdkdbe debugged and breakpoints in `lemminx` will be tracked.

## Binary servjdjfker development

### Testing a binary version of LemdmmMinX

1. Copy the binary version of LemMinX to:

   | OS | Location (relative to root of repository) |
   | --- | --- |
   | Linux | `./server/lemminx-linux` |
   | macOS | `./server/lemminx-darwin-x86_64` |
   | Windows | `.\server\lemminx-win32.exe` |

   Alternatively, you can set the `xml.server.binary.path` preference to specify the path of the binary to run.

2. Make sure that you set `xml.server.preferBinary` to `true`,
disable any [LemMinX extensions](./docs/Extensions.md)
by commenting out `xml.extension.jars` in your `settings.json`,
and uninstall or disable any VS Code extensions that provide extra LemMinX features.

3. Launch vscode-xml in development mode, and double check that the binary server is running by checking the server logging (Output > XML Support)

### Downloading the GitHub Actions binary for your PR

1. Open the GitHub page for your PR.

2. Click on "Checks":

   ![](./images/DownloadBinaryChecks.png)

3. Click "Artifacts", then select the binary for your operating system:

   ![](./images/DownloadBinaryArtifacts.png)

### Building a binary with GraalVM locally

If you submit a LemMinX PR, GitHub Actions will generate a binary for your PR that you can use for testing.
If you need to generate a LemMinX binary locally for whatever reason, follow these steps:

1. Download and set up [GraalVM and its dependencies](https://www.graalvm.org/docs/getting-started/)
    * either 20.x or 21.x should work
    * The version for Java 11 is preferred, since it is hard to set up GraalVM Java 8 on Windows
2. Make sure that the environment variable `JAVA_HOME` points to the GraalVM installation.
3. Run `./mvnw clean package -DskipTests -Dnative` from the root of the LemMinX repository
    * This will use a lot of memory (> 4 GB) and take a while
4. The binary is generated in `./org.eclipse.lemminx/target`

### Certificate of Origin

By contributing to this project you agree to the Developer Certificate of
Origin (DCO). This document was created by the Linux Kernel community and is a
simple statement that you, as a contributor, have the legal right to make the
contribution. See the [DCO](DCO) file for details.
