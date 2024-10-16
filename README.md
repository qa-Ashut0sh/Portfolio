import React from 'react';
import { Download, ExternalLink } from 'lucide-react';

const Section = ({ title, children }) => (
  <div className="mb-8">
    <h2 className="text-2xl font-bold mb-4 border-b pb-2">{title}</h2>
    {children}
  </div>
);

const ListItem = ({ children }) => (
  <li className="mb-2 flex items-start">
    <span className="mr-2">•</span>
    <span>{children}</span>
  </li>
);

const Portfolio = () => {
  return (
    <div className="max-w-4xl mx-auto p-6 bg-white shadow-lg rounded-lg">
      <h1 className="text-4xl font-bold mb-6 text-center">Portfolio</h1>
      
      <nav className="mb-8">
        <ul className="flex flex-wrap justify-center gap-4">
          {['About me', 'CV', 'Skills', 'Tools', 'Examples of my work', 'Additional Points'].map((item) => (
            <li key={item}>
              <a href={`#${item.toLowerCase().replace(/\s+/g, '-')}`} className="text-blue-600 hover:underline">
                {item}
              </a>
            </li>
          ))}
        </ul>
      </nav>

      <Section title="About me">
        <ul className="list-disc pl-6">
          <ListItem>Pro QA Engineer with <strong>4 years</strong> of experience in Software Testing for both Web and Mobile applications.</ListItem>
          <ListItem>Expertise in various testing areas, including <strong>API</strong>, <strong>UI</strong>, <strong>Performance</strong> and <strong>Database</strong>, ensuring thorough and practical testing.</ListItem>
          {/* Add other list items here */}
        </ul>
      </Section>

      <Section title="CV">
        <p className="flex items-center">
          You can download/view my CV as <a href="https://drive.google.com/file/d/1NBc3MRE4p3ghdxgm7DsKpSUhryHjjR6H/view?usp=drive_link" target="_blank" rel="noopener noreferrer" className="text-blue-600 hover:underline ml-2 flex items-center">
            PDF File <Download className="w-4 h-4 ml-1" />
          </a>
        </p>
      </Section>

      <Section title="Skills">
        <p className="mb-4">You can find examples of the described skills in the <a href="#examples-of-my-work" className="text-blue-600 hover:underline">Example of my work</a> section.</p>
        
        {['UI testing', 'API testing', 'Performance testing', 'Test analysis & design', 'Test documentation', 'Database Testing using SQL', 'Automation Testing using Selenium, Selenium IDE, Eclipse, IntelliJ', 'Mobile Testing using Appium, Katalon'].map((skill) => (
          <div key={skill} className="mb-4">
            <h3 className="font-semibold mb-2">{skill}</h3>
            <ul className="list-disc pl-6">
              <ListItem>Skill description 1</ListItem>
              <ListItem>Skill description 2</ListItem>
              <ListItem>Skill description 3</ListItem>
            </ul>
          </div>
        ))}
      </Section>

      <Section title="Tools">
        {[
          { category: "Bug Mangements", tools: ["Jira", "Bugzilla", "Azure Devops"] },
          { category: "API Testing", tools: ["Postman", "SoapUI"] },
          { category: "Load Testing", tools: ["Gatling", "JMeter"] },
          { category: "Database Testing", tools: ["MySQL"] }
        ].map((category) => (
          <div key={category.category} className="mb-4">
            <h3 className="font-semibold mb-2">{category.category}</h3>
            <ul className="list-disc pl-6">
              {category.tools.map((tool) => (
                <ListItem key={tool}>{tool}</ListItem>
              ))}
            </ul>
          </div>
        ))}
      </Section>

      <Section title="Examples of my work">
        <h3 className="font-semibold mb-2">Bug reports and test cases of work in Jira</h3>
        <h4 className="font-medium mb-2">Bugs</h4>
        <p className="mb-2">The below sample bugs are found in my last project, which was a shipping domain and reported in Jira:</p>
        <ul className="list-disc pl-6 mb-4">
          {[1, 2, 3].map((num) => (
            <ListItem key={num}>
              Bug #{num}. Check <a href={`https://drive.google.com/file/d/1MF5nk3PN2rTo6es-ggwOkSqdpWVecqx4/view?usp=sharing`} target="_blank" rel="noopener noreferrer" className="text-blue-600 hover:underline">the screenshot of the bug report in Jira</a>.
            </ListItem>
          ))}
          <ListItem>
            Bug #4. Check <a href="https://drive.google.com/file/d/1fk3bcbl1xE30lTPcUKn9MsKEGv1bPFjh/view?usp=sharing" target="_blank" rel="noopener noreferrer" className="text-blue-600 hover:underline">the screenshot of the bug report in Azure DevOps</a>.
          </ListItem>
        </ul>
        <h4 className="font-medium mb-2">Test Cases</h4>
        <p>
          Here is a <a href="https://drive.google.com/file/d/1zvLkq5kLjTCiXM7apNjEXdVb1q9SAZMO/view?usp=drive_link" target="_blank" rel="noopener noreferrer" className="text-blue-600 hover:underline">pdf file</a>, where you can view my sample test cases for all types of testing like API, UI and SQL.
        </p>
      </Section>

      <Section title="Additional Points">
        <p className="mb-4">
          I am also working as a freelancer/part-time blog article writer for one of my <a href="https://automatenow.io/" target="_blank" rel="noopener noreferrer" className="text-blue-600 hover:underline flex items-center">US client <ExternalLink className="w-4 h-4 ml-1" /></a>, written over 70+ articles in tech domain.
        </p>
        <ul className="list-disc pl-6">
          {[1, 2, 3].map((num) => (
            <ListItem key={num}>
              <a href={`https://automatenow.io/sample-article-${num}`} target="_blank" rel="noopener noreferrer" className="text-blue-600 hover:underline flex items-center">
                Sample article #{num} <ExternalLink className="w-4 h-4 ml-1" />
              </a>
            </ListItem>
          ))}
        </ul>
      </Section>
    </div>
  );
};

export default Portfolio;
