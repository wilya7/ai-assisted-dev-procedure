# AI-Assisted Software Development Procedure

A systematic procedure for developing research-grade data science tools using human-LLM collaboration.

## Overview

This repository contains a comprehensive, battle-tested procedure for systematic AI-assisted software development in data science. The methodology emphasizes thorough upfront planning to minimize debugging time and maximize learning value through granular, testable code units.

## Key Features

- **Systematic Design Thinking**: 67% of project time invested in upfront design
- **Learning-Focused Implementation**: Granular code units optimized for skill development
- **Research-Grade Quality**: Comprehensive testing and documentation standards
- **Human-LLM Collaboration Framework**: Clear handoff specifications for each phase
- **Failure Mode Analysis**: Proactive identification of potential problems

## Methodology Phases

1. **Project Bootstrap** (25% of time)
   - Goal clarification through handwritten intent documents
   - Negative space mapping using Socratic failure mode analysis

2. **Specification Development** (40% of time)
   - Technical specification brainstorming
   - Iterative validation and refinement

3. **Atomic Unit Decomposition** (15% of time)
   - Breaking specifications into incremental, testable units
   - Creating prompt engineering guides

4. **Systematic Code Development** (15% of time)
   - Per-unit development workflow
   - Integration milestones and testing

5. **Quality Assurance** (5% of time)
   - Final integration testing
   - Documentation finalization

## Quick Start

1. Read the complete procedure in [`docs/procedure.md`](docs/procedure.md)
2. Start with Phase 1.1: handwrite your intent document
3. Follow the systematic workflow through all phases
4. Use the templates in [`templates/`](templates/) for structured documents

## Time Investment Philosophy

The procedure front-loads design work (Phases 1-2 consume ~67% of total time) to dramatically reduce debugging and rework time in later phases. This approach makes total development time shorter and more predictable.

## Success Criteria

A project is successful when:
- ✅ All units pass individual tests
- ✅ Complete pipeline processes realistic data
- ✅ Code is readable and well-documented
- ✅ Repository follows research-grade standards
- ✅ Author can explain every component confidently
- ✅ Tool addresses original problem statement

## Repository Structure

```
ai-assisted-dev-procedure/
├── README.md
├── LICENSE
├── docs/
│   ├── procedure.md          # Complete methodology
│   └── examples/            # Real-world usage examples
├── templates/
│   ├── intent-document.md   # Phase 1.1 template
│   ├── negative-space.md    # Phase 1.2 template
│   └── specifications.md    # Phase 2 template
├── examples/
│   └── sample-projects/     # Complete example implementations
└── src/
    └── procedure.org        # Original org-mode source
```

## Contributing

This is a living document that improves through real-world testing. To contribute:

1. Test the procedure on actual projects
2. Document what works and what needs improvement
3. Submit issues or pull requests with specific improvements
4. Include your testing experience and specific areas for refinement

## Version History

- **v1.0**: Initial systematic procedure based on practical testing
- **Living Document**: Continuously refined based on user experience

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Citation

If you use this methodology in your research or projects, please cite:

```
AI-Assisted Software Development Procedure
https://github.com/[your-username]/ai-assisted-dev-procedure
```

## Support

- 📖 Read the full documentation in [`docs/procedure.md`](docs/procedure.md)
- 💡 Check existing issues for common questions
- 🐛 Report bugs or suggest improvements via GitHub issues
- 🤝 Contribute improvements based on your testing experience

---

*"The procedure alternates between deep human thinking and collaborative human-LLM work, ensuring both cognitive rigor and implementation efficiency."*