<template>
  <main class="container">
    <div id="resume" class="d-flex">
      <div class="left-col">
        <div class="resume-section">
        <h4 class="section-headline">
          About me
        </h4>
        <div>
          From data cleanining to data analysis to machine learning, I am passionate about evrything data.
        </div>
      </div>

      <div class="resume-section">
        <h4 class="section-headline">
          Contact
        </h4>
        <ul>
          <li>12345678</li>
          <li>mail@gmail.com</li>
          <li>Tunis Ariana ,9999 place</li>
        </ul>
      </div>

      <div class="resume-section">
        <h4 class="section-headline">
          Skills
        </h4>
        <ul>
          <li>Python</li>
          <li>Pandas</li>
          <li>SQL</li>
          <li>TypeScript</li>
          <li>Java</li>
          <li>C</li>
        </ul>
      </div>

      <div class="resume-section">
        <h4 class="section-headline">
          Certifications
        </h4>
        <ul>
          <li>Natural language processing with python (corsera)</li>
        </ul>
      </div>

      </div>
      <div class="right-col">
        <div class="personal-name">
          Tej Eddine Benamor
        </div>
        <div class="personal-title">
          Computer Science Student
        </div> 
        <div class="resume-section">
          <h4 class="section-headline">
          Experience
        </h4>
        <div>Studying</div>
        <ul>
          <li>3rd year Studying</li>
        </ul>
        <h4 class="section-headline">
          Education
        </h4>
        <div>
          License Computer Science
        </div>
        <div>High School degree in Technologie</div>
        </div>
      </div>

    </div>
  </main>
</template>

<style scoped>
#resume {
  box-shadow: rgba(50, 50, 93, 0.25) 0px 13px 27px -5px,rgba(0, 0, 0, 0.3) 0px 8px 16px -8px;

  height: 297mm;
  width: 210mm;
}
.left-col{
  background-color: var(--background-color-left);
  color: var(--text-color-left);
  border-right: 1px solid var(--highlight-color-left);
  width: 30%;
  padding: 30px;
}
.right-col{
  background-color: var(--background-color-right);
  color: var(--text-color-right);
  width: 70%;
  padding: 30px ; 
}
.section-headline{
  font-size: 20px;
  font-weight: var(--headline-weight);
  margin-bottom: 15px;
  margin-top: 0;
}
.right-col .section-headline{
  color: var(--highlight-color-right);
}
.left-col .section-headline{
  border-bottom: 1px solid var(--highlight-color-left);
  padding-bottom: 5px;
  margin-right: -30px;
  padding-right: 10px;
  color: var(--highlight-color-left);
}
.rsume-section{
  margin-bottom: 30px;
}

</style>
