### Theme architecture — Starterkit and base theme

- **Decision:** Use Drupal Core's **Starterkit Theme** generator to create the custom `grazer` theme.
- **Command used:** `php core/scripts/drupal generate-theme grazer ...`
- **Location:** `web/themes/custom/grazer`
- **Rationale:** Starterkit provides a current Drupal-compatible starting structure while allowing the generated theme to become an independent custom theme owned by the project.

- **Base theme decision:** Do **not** use a runtime base-theme dependency.
- The generated `grazer` theme is based on a snapshot of Drupal's `starterkit_theme` at generation time rather than remaining a child theme of Starterkit.
- This avoids coupling the project to changes in a parent theme and gives the project full control over templates, CSS, JavaScript, libraries, and theme configuration.
- The generated theme therefore uses `base theme: false` in `grazer.info.yml`.

- **Implementation note:** An initial generation attempt placed the theme outside the intended custom theme directory because multiline shell arguments were interpreted incorrectly. The generated files were removed and the theme was regenerated correctly under `web/themes/custom/grazer`.

- **Source-control decision:** `web/themes/custom/grazer` is project-owned code and should be committed to Git. Drupal core, Composer dependencies, and contributed themes/modules remain Composer-managed and are excluded through `.gitignore`.

- **Current direction:** Treat `grazer` as the project's standalone design-system/theme implementation layer, with project-specific Twig templates, component styles, libraries, and Drupal theme integration maintained directly in this repository.

<img alt="Drupal Logo" src="https://www.drupal.org/files/Wordmark_blue_RGB.png" height="60px">

Drupal is an open source content management platform supporting a variety of
websites ranging from personal weblogs to large community-driven websites. For
more information, visit the Drupal website, [Drupal.org][Drupal.org], and join
the [Drupal community][Drupal community].

## Contributing

Drupal is developed on [Drupal.org][Drupal.org], the home of the international
Drupal community since 2001!

[Drupal.org][Drupal.org] hosts Drupal's [GitLab repository][GitLab repository],
its [issue queue][issue queue], and its [documentation][documentation]. Before
you start working on code, be sure to search the [issue queue][issue queue] and
create an issue if your aren't able to find an existing issue.

Every issue on Drupal.org automatically creates a new community-accessible fork
that you can contribute to. Learn more about the code contribution process on
the [Issue forks & merge requests page][issue forks].

## Usage

For a brief introduction, see [USAGE.txt](/core/USAGE.txt). You can also find
guides, API references, and more by visiting Drupal's [documentation
page][documentation].

You can quickly extend Drupal's core feature set by installing any of its
[thousands of free and open source modules][modules]. With Drupal and its
module ecosystem, you can often build most or all of what your project needs
before writing a single line of code.

## Changelog

Drupal keeps detailed [change records][changelog]. You can search Drupal's
changes for a record of every notable breaking change and new feature since
2011.

## Security

For a list of security announcements, see the [Security advisories
page][Security advisories] (available as [an RSS feed][security RSS]). This
page also describes how to subscribe to these announcements via email.

For information about the Drupal security process, or to find out how to report
a potential security issue to the Drupal security team, see the [Security team
page][security team].

## Need a helping hand?

Visit the [Support page][support] or browse [over a thousand Drupal
providers][service providers] offering design, strategy, development, and
hosting services.

## Legal matters

Know your rights when using Drupal by reading Drupal core's
[license](/core/LICENSE.txt).

Learn about the [Drupal trademark and logo policy here][trademark].

[Drupal.org]: https://www.drupal.org
[Drupal community]: https://www.drupal.org/community
[GitLab repository]: https://git.drupalcode.org/project/drupal
[issue queue]: https://www.drupal.org/project/issues/drupal
[issue forks]: https://www.drupal.org/drupalorg/docs/gitlab-integration/issue-forks-merge-requests
[documentation]: https://www.drupal.org/documentation
[changelog]: https://www.drupal.org/list-changes/drupal
[modules]: https://www.drupal.org/project/project_module
[security advisories]: https://www.drupal.org/security
[security RSS]: https://www.drupal.org/security/rss.xml
[security team]: https://www.drupal.org/drupal-security-team
[service providers]: https://www.drupal.org/drupal-services
[support]: https://www.drupal.org/support
[trademark]: https://www.drupal.com/trademark
