# DOSW Laboratory 3 — README Project

**Course:** DOSW — Software Development and Operations

**Institution:** Escuela Colombiana de Ingeniería Julio Garavito

**Activity:** Express Hackathon 2026-2

**Work Mode:** Teams of three students

---

### Team Information & Contributions

| Name | GitHub Username |
| --- |-----------------|
| Daniel Santiago Morales Perdomo | `Fukuyaku88`    |
| Edgar Daniel Ruiz Patiño | `DaniRuiz11`    |
| Miguel Ángel Acero Laverde | `Miguelim101`   |

### PART 1 - Project Structure

1. **What is a Maven Archetype?**
* **Answer:**
  A Maven Archetype is a project template used by Maven to generate new projects with a predefined structure and configuration. It allows developers to create projects consistently and quickly, following a particular organization or set of best practices.
2. **What is the purpose of the maven-archetype-quickstart archetype?**
* **Answer:**
  The **maven-archetype-quickstart** archetype is used to generate a basic Maven project as a starting point for development. It creates a standard project structure that includes the necessary Maven configuration and an example Java application and test.
3. **What command can be used to create a project based on a Maven archetype?**
* **Answer:**
  The main command is:*
    * mvn archetype:generate

  For example, to create a project using maven-archetype-quickstart:
    * mvn archetype:generate \
      -DgroupId=edu.eci.dosw.lab \
      -DartifactId=DOSW-Lab3 \
      -DarchetypeArtifactId=maven-arquetype-quickstart \
      -DarchetypeVersion=1.0 \
      -DinteractiveMode=false

      The **archetype:generate** goal generates a new Maven project from an archetype template.
4. **What is a pull request in GitHub?**
* **Answer:**
  A pull request (PR) in GitHub is a proposal to merge changes from one branch into another branch of a repository. It provides a space where collaborators can review the changes, discuss them, request modifications, and approve them before the changes are merged.
5. **How do you create a pull request in GitHub?**
* **Answer:**
    1. Create a separate branch and make the required changes.
    2. Commit the changes.
    3. Push the branch to GitHub.
    4. Open the repository on GitHub.
    5. Select **Pull requests**.
    6. Click **New pull request**.
    7. Select the **base branch**, which is the branch where the changes should be merged.
    8. Select the **comparator branch**, which contains your changes.
    9. Review the changes.
    10. Enter a tittle and description.
    11. Click **Create pull request**.

  For example, the basic Git commands before creating the PR are:
    * git add .
    * git commit -m "target: Describe the changes"
    * git push feature/proj-requirements origin feature/proj-requirements

6. **How do you approve a pull request in GitHub?**
* **Answer:**
    1. Open the repository on GitHub. Go to Pull requests.
    2. Select the pull request you want to review.
    3. Open the Files changed tab.
    4. Review the proposed changes.
    5. Click Review changes.
    6. Select Approve.
    7. Optionally add a comment explaining the review.
    8. Click Submit review.

  Selecting **Approve** indicates that the reviewer considers the changes ready to be merged. Whether the PR can actually be merged may also depend on repository rules, required reviews, and automated checks.
7. **Include the bibliography, using APA format, for the sources consulted to answer the questions above.**
* **Answer:**

Apache Maven. (n.d.). Introduction to archetypes. Apache Software Foundation. https://maven.apache.org/guides/introduction/introduction-to-archetypes.html

Apache Maven. (n.d.). Maven in 5 minutes. Apache Software Foundation. https://maven.apache.org/guides/getting-started/maven-in-five-minutes

GitHub. (n.d.). About pull requests. GitHub Docs. https://docs.github.com/en/pull-requests/get-started/about-pull-requests

GitHub. (n.d.). Quickstart for pull requests. GitHub Docs. https://docs.github.com/en/pull-requests/get-started/pull-request-quickstart

GitHub. (n.d.). Quickstart for reviewing pull requests. GitHub Docs. https://docs.github.com/en/pull-requests/get-started/reviewing-pull-requests-quickstart