# Contributing to Auric Tamil Radio Bot

First off, thanks for taking the time to contribute! 🎉

The following is a set of guidelines for contributing to Auric Tamil Radio Bot. These are mostly guidelines, not rules. Use your best judgment, and feel free to propose changes to this document in a pull request.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Style Guidelines](#style-guidelines)

## Code of Conduct

This project and everyone participating in it is governed by our commitment to creating a welcoming and inclusive environment. By participating, you are expected to uphold this standard.

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check the issue list as you might find that you don't need to create one. When you are creating a bug report, please include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples to demonstrate the steps**
- **Describe the behavior you observed after following the steps**
- **Explain which behavior you expected to see instead and why**
- **Include screenshots if helpful**

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, please include:

- **Use a clear and descriptive title**
- **Provide a step-by-step description of the suggested enhancement**
- **Provide specific examples to demonstrate the steps**
- **Describe the current behavior and explain which behavior you expected to see instead**
- **Explain why this enhancement would be useful**

### Adding New Radio Stations

We're always looking to expand our station list! To add a new station:

1. Ensure the stream URL is stable and publicly accessible
2. Test the stream with FFmpeg to verify compatibility
3. Add the station to the `radio_stations` list in `main.py`
4. Include appropriate metadata (name, image URL)
5. Test the station thoroughly before submitting

### Code Contributions

1. Fork the repository
2. Create a new branch from `main`
3. Make your changes
4. Test your changes thoroughly
5. Submit a pull request

## Development Setup

1. **Prerequisites**
   ```bash
   # Install Python 3.8+
   # Install FFmpeg
   # Get a Discord Bot Token
   ```

2. **Clone and setup**
   ```bash
   git clone https://github.com/NirmaLKumar26/Auric-Tamil-FM-Radio.git
   cd Auric-Tamil-FM-Radio
   pip install -r requirements.txt
   ```

3. **Configuration**
   - Replace the bot token in `main.py`
   - Update any hardcoded user IDs for testing
   - Test in a development Discord server

4. **Testing**
   - Test all commands (`/play`, `/stop`, `/list`, etc.)
   - Test with multiple radio stations
   - Test error scenarios (invalid streams, network issues)
   - Test multi-server functionality

## Pull Request Process

1. **Update documentation** if you're changing functionality
2. **Follow the code style guidelines** below
3. **Test your changes** thoroughly
4. **Update the README.md** if you're adding features
5. **One feature per pull request** - keep PRs focused

### Pull Request Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
- [ ] Tested with multiple radio stations
- [ ] Tested error scenarios
- [ ] Tested in multiple Discord servers

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] No new warnings/errors
```

## Style Guidelines

### Python Code Style

- Follow **PEP 8** guidelines
- Use **4 spaces** for indentation
- **Maximum line length**: 100 characters
- Use **descriptive variable names**
- Add **docstrings** for functions

### Error Handling

```python
# Good
try:
    result = some_operation()
    logger.info(f"Operation successful: {result}")
except SomeSpecificError as e:
    logger.error(f"Specific error occurred: {e}")
    # Handle gracefully
except Exception as e:
    logger.error(f"Unexpected error: {e}")
    # Fallback behavior
```

### Logging

```python
# Use appropriate log levels
logger.debug("Detailed debugging information")
logger.info("General information")
logger.warning("Warning about potential issues")
logger.error("Error that needs attention")
```

### Async/Await

```python
# Prefer async/await over callbacks
async def good_function():
    try:
        result = await some_async_operation()
        return result
    except Exception as e:
        logger.error(f"Error in good_function: {e}")
        raise
```

## Commit Message Guidelines

- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit the first line to 72 characters or less
- Reference issues and pull requests liberally after the first line

### Examples

```
Add support for new radio station format

- Implement parsing for M3U8 playlists
- Add validation for stream URLs
- Update documentation for station format

Fixes #123
```

## Recognition

Contributors will be recognized in the README.md file and release notes. We appreciate all contributions, no matter how small!

## Questions?

Feel free to contact the maintainers if you have any questions:

- Create an issue for general questions
- Join our Discord server for real-time chat
- Email the maintainers for private concerns

Thank you for contributing to Auric Tamil Radio Bot! 🎵
