# GitHub Issue Forms

GitHub supports web form fields in issue templates:

```yaml
name: Feature request
description: Suggest an idea for this project
body:
  - type: markdown
    attributes:
      value: |
        Thanks for taking the time to fill out this feature report!
  - type: textarea
    id: feature-description
    attributes:
      label: Description
      description: "A clear and concise description of what the problem is."
      placeholder: Ex. I'm always frustrated when [...].
    validations:
      required: true
```

This will render the below form:

![Screenshot 2023-12-10 at 9 59 16 PM](https://github.com/petermekhaeil/til/assets/4616064/bdf28f4e-bc6c-4303-a789-8b2c3b9b9c09)

## Learn More
- [Documentation](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository#creating-issue-forms)
- [Syntax for GitHub's form schema](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-githubs-form-schema)
