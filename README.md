**Introduction**
1) Deprived of fundamental right “Right to Education” for differently abled(hearing aid).
2) Providing equal opportunities for the deaf and hard of hearing community to excel in technology and coding careers.
3) Fostering a more inclusive tech industry by integrating ISL users into coding communities and workplaces.
4) Removing linguistic obstacles by making programming education accessible to ISL users.

**Problem Statement**
1) We have programming textbooks in English Language.
2) We are trying to convert those into Indian Sign Language.

**Motivation**
1) Limited Access to Programming Education for the Deaf and Hard of Hearing:
Deaf and hard of hearing individuals face significant barriers in accessing programming literature and online resources, which are predominantly available in English.
2) Lack of Inclusive Learning Resources:
Existing programming education materials, including textbooks, online tutorials, and coding platforms, rarely offer comprehensive support for Indian Sign Language (ISL) users. The absence of ISL-compatible resources hampers effective learning and skill development for the deaf and hard of hearing community interested in programming.
3) Communication Gap Hindering Skill Development:
The absence of a reliable translation system between English and ISL prevents effective communication of programming concepts, coding instructions, and technical documentation. - This communication gap impedes the development of programming skills among individuals who rely on ISL, limiting their ability to participate fully in the digital economy.

**Objective**
1) Our overall objective is to provide an aid to deaf students 
2) Translating the lecture material into ISL Glosses.
3) Aid generic machine translation with all the challenges like code snippets.

**Approach**
1) Extracting text file from a PDF file that contains all the sentences from a specific chapter of the textbook.
2) Using ,Patel Raj Nath [1]  ,reordering rules as our baseline for machine translation.
3) Various regular expression used for identifying both assigned  and declared variables, Data types (int ,float,double..), UDT (struct ,classes ..) and Function Names to prevent them from reordering. 
4) Developing pre and post processing with the above baseline

**Methodology**
1) Development of a PDF extraction tool that extracts the sentences from a PDF file and make some post processing on the extracted sentences for the cleansing and filtering of inappropriate words.
2) Development of PoS taggers for reserved keywords and identifiers of C programming language.
3) Development of post-processing method to utilize these tags to make the text more understandable (e.g. wherever it identifies a function name it adds (); printf())
4) Development of rule based spell correction, where along with nouns, terms specific to C programming
5) Development of a method to identify code snippets within text and prevent them to convert in ISL form.  

3.1 Overall Description of Project
3.11 Challenges in Integrating Dynamic Improvement with Current Standalone Functionality for English to ISL Conversion Application
  ❖	Current Standalone Functionality:
    ●	The English to ISL Conversion application currently operates independently.
    ●	Users provide English sentences as input, and the application processes them in isolation.
    ●	The system functions as a standalone entity without direct interaction with external software or databases.
  ❖	User Interaction:
    ●	Users initiate the application by inputting English sentences.
    ●	The application processes the input to generate corresponding outputs in ISL (Indian Sign Language).
  ❖	Technical Isolation: 
    ●	The application does not integrate with other software systems.
    ●	No interaction with external APIs or databases for linguistic resources or real-time updates.
  ❖	Simplicity vs. Dynamic Improvement:
    ●	While the standalone approach offers simplicity and user-friendly operation,
    ●	It may limit the application from benefiting from real-time updates or dynamic improvements derived from external linguistic databases.
3.12 Web-Based Multilingual Translation Platform:
Our project constitutes a dynamic web-based application designed to facilitate seamless language translation with a multifaceted approach. The application comprises two primary functionalities: the Quick Translation feature and the File Translation module, each catering to distinct user needs.
  ❖	Quick Translation:
    In the Quick Translation section, users engage with an intuitive interface where they input sentences in English. The application swiftly processes this input, generating translations in Indian Sign Language (ISL), as well as reordered and Hindi sentences. This real-time translation feature ensures a rapid and user-friendly experience, making language conversion effortlessly accessible.
  ❖	File Translation:
    The File Translation component extends the application's capabilities to handle larger volumes of text. Users upload preprocessed text files, and the system efficiently processes the content, producing an
    ISL-generated text file. This functionality is particularly valuable for users dealing with comprehensive documents or extended texts, offering a streamlined solution for batch translation.
  ❖	User-Friendly Interface:
    The web interface ensures a user-friendly experience, guiding individuals through the translation process with simplicity and clarity. The seamless integration of both quick and file translation functionalities enhances the versatility of the platform, catering to diverse user preferences and requirements.
  ❖	Real-Time Accessibility:
    Users can access the translated outputs directly on our webpage, facilitating immediate communication in multiple languages. The platform's efficiency lies in its ability to bridge linguistic gaps quickly and effectively, whether for single sentences or entire documents.

3.2 Requirement Analysis
Functional Requirements
  ❖	Text Extraction:
    The system should be able to extract text from the provided programming literature, specifically the book "The C Programming Language" by Brian and Dennis Ritchie.
  ❖	Tokenization:
    Implement tokenization using the Natural Language Toolkit (NLTK) to break down the extracted text into individual tokens, such as words and punctuation.
  ❖	Lemmatization:
    Utilize the NLTK library to perform lemmatization on the tokens, ensuring that words are reduced to their base or root form for accurate translation.
  ❖	Wordnet Integration:
    Integrate WordNet with the system to enhance the accuracy of word meanings and relationships during the translation process.
  ❖	Spell Checking:
    Incorporate a spell checker to identify and correct spelling errors in the extracted text, improving the overall quality of the translated content.
  ❖	Translation (English to Hindi):
    Use the "englisttohindi" library to translate the English sentences from the programming literature into Hindi.
  ❖	User Interface:
    Develop a user-friendly interface that allows users to input the programming literature and initiate the translation process.
  ❖	Output Presentation:
    Present the translated content in a readable format, either through the user interface or as a separate file, maintaining the original formatting of the text.
Non-Functional Requirements
  ❖	Performance:
    The system should process the provided programming literature efficiently, ensuring reasonable response times for both tokenization and translation.
  ❖	Scalability:
    Design the system to handle varying lengths of input text, accommodating different sizes of programming literature without compromising performance.
  ❖	Reliability:
    Ensure the reliability of the translation process, minimizing errors and inaccuracies in the final translated content.
  ❖	Compatibility:
    The system should be compatible with popular Python IDEs such as IDLE and Thonny, allowing seamless integration into the development environment. ❖ Usability:
    Create an intuitive and user-friendly interface that enables users, including those with limited technical knowledge, to easily interact with and utilize the translation system.
  ❖	Maintainability:
    Design the system with modular and well-documented code to facilitate future updates, enhancements, and maintenance.
  ❖	Security:
    Implement security measures to protect user data and ensure the confidentiality of the programming literature being processed.
  ❖	Documentation:
    Provide comprehensive documentation, including user guides and technical documentation, to assist users in understanding and utilizing the system effectively.
  ❖	Testing:
    Conduct thorough testing, including unit testing and integration testing, to verify the correctness and reliability of each component in the system.
By addressing these functional and non-functional requirements, the translation project can effectively meet the user's needs while ensuring performance, reliability, and usability.

3.3 Solution And Approach
Our solution focuses on code translation, spell checking, and syntactic analysis for multilingualization in software development. It aims to facilitate collaboration among developers with diverse linguistic backgrounds. 
3.31 Code Translation
  ❖	Spell Checking:
    Our solution incorporates the SpellChecker library to enhance the accuracy of the code translation process by identifying and correcting spelling errors. This spell-checking mechanism, however, is refined to exclude certain word types from the correction process. The exclusion criteria encompass specific categories of words, such as nouns, symbols, and other contextually irrelevant terms.
    By excluding these word types, we aim to ensure that essential programming elements and symbols remain untouched during the spell-checking phase. This strategic approach prevents unintended modifications to critical components of the code, preserving the syntactic and semantic integrity of the original programming constructs.
  ❖	Plural to Singular Conversion:
    Our solution employs WordNet-based lemmatization to seamlessly handle plural-to-singular conversion within the code. Leveraging the rich lexical database of WordNet, this approach identifies and transforms plural forms of words into their corresponding singular counterparts. By utilizing lemmatization, the system ensures a linguistically informed conversion process, considering the grammatical nuances of each word. This enhances the overall precision of the translation, providing an effective means to reconcile variations in word forms and contribute to the coherence of the translated code.
  ❖	Verb Form Conversion:
    In the process of code translation, our solution harnesses the power of the WordNet lemmatizer to convert verb forms to their base forms. Leveraging WordNet's extensive lexical knowledge, the lemmatizer identifies the root or base form of verbs, ensuring a standardized representation in the translated code. This approach is crucial for maintaining the syntactic accuracy of the codebase, as it harmonizes varied verb conjugations into a consistent and comprehensible structure. By adopting WordNet lemmatization, our solution contributes to the clarity and uniformity of the translated code, facilitating better understanding across diverse linguistic contexts.
  ❖	Translation of Comments:
    Our solution incorporates the Translator library to proficiently translate both single-line and multi-line comments within the code. By leveraging this translation tool, we ensure that descriptive comments, crucial for code comprehension, are accurately transformed while maintaining their original context. This capability extends to handling diverse comment structures, enhancing the multilingualization of code documentation. The Translator library facilitates a seamless transition of comments, contributing to improved collaboration and understanding across language barriers.
  ❖	Translation of Reserved Words:
    To enhance code multilingualization, our solution maps reserved C keywords to their Hindi equivalents. By establishing a predefined dictionary, the system identifies and replaces these keywords with their linguistically equivalent counterparts. This mapping ensures that fundamental programming terms retain their semantic meaning, facilitating a smooth transition between English and Hindi. The meticulous translation of reserved words is a key step in making the code more accessible and comprehensible to developers with varied linguistic backgrounds.
  ❖	Syntax Reordering:
    For optimal Hindi language compatibility, our solution strategically reorders English syntax to adhere to the Subject-Object-Verb (SOV) structure. This transformation ensures that the translated code aligns with Hindi language conventions, where the subject typically precedes the object and the verb comes last. By implementing SOV form, our approach not only enhances linguistic coherence but also facilitates a more natural and contextually fitting translation of code, promoting seamless understanding for developers proficient in Hindi.
3.32 Syntactic Analysis and Correction
  ❖	Sentence Splitting:
    To navigate complex sentence structures, our solution intelligently splits sentences based on conjunctions. This approach facilitates a granular analysis, allowing the system to handle intricate sentence formations by recognizing and isolating distinct clauses. By strategically employing conjunction-based sentence splitting, our solution enhances syntactic analysis and ensures accurate processing of complex language structures within the code.
  ❖	Part-of-Speech Filtering:
    Our solution employs part-of-speech tagging to meticulously filter out unnecessary words from the code. By categorizing words based on their grammatical roles, the system identifies and excludes non-essential elements, streamlining the code for improved readability and analysis. This targeted filtering enhances the precision of syntactic analysis while maintaining the code's structural integrity.
  ❖	Variable and Function Name Extraction:
    Our solution incorporates an intelligent mechanism to identify user-declared variables, data types, User-Defined Types (UDTs), and function names within the code. By employing syntactic analysis, the system precisely extracts these essential elements, providing valuable insights into the code structure. This extraction process not only aids in language translation but also facilitates a comprehensive understanding of the code's composition, supporting developers in comprehending and collaborating on multilingual codebases.
  ❖	Code Structure Preservation:
    Our solution prioritizes the preservation of structural integrity throughout the translation and analysis process. By meticulously handling sentence splitting, part-of-speech filtering, and syntactic analysis, the system guarantees that the fundamental structure of the code remains intact. This commitment to structural preservation ensures that the translated code maintains its original organizational coherence, facilitating seamless collaboration and comprehension across language variations.
3.33 Anonymous Code Block Handling
  ❖	Identification and Separation:
    Our solution adeptly recognizes and isolates anonymous code blocks enclosed within curly braces. By implementing a sophisticated algorithm, the system effectively identifies these blocks, allowing for targeted translation and analysis of contained code segments. This recognition and separation mechanism contribute to the accurate handling of code structures, ensuring precise translation and preserving the integrity of anonymous blocks.
  ❖	Translation and Analysis:
    Our solution seamlessly applies the established translation pipeline to each identified anonymous code block. This ensures that the translation process is systematically extended to preserve the original structure of these code segments. By maintaining the integrity of anonymous blocks, the system guarantees that the translated code remains faithful to the intricacies of the source code.
  ❖	Code Structure Preservation:
    Our solution places a paramount emphasis on maintaining the structural integrity of translated anonymous code blocks. By meticulous translation and adherence to the original coding structure, the system ensures that the translated code retains its inherent organization. This commitment to structural preservation enhances code comprehensibility and fosters smooth collaboration across language barriers.
3.34 Multilingualization of Code
  ❖	Hindi Translation:
    Our solution leverages EngtoHindi for translating English code into Hindi, enriching the process with part-of-speech tagging. This integration ensures not only accurate language conversion but also a nuanced understanding of the grammatical context. By incorporating part-of-speech tagging, the system refines the translation, producing code in Hindi that aligns with the linguistic nuances of the target language.
  ❖	Output Generation:
    Our solution generates a comprehensive set of outputs, including reordered English code, translated code, and the corresponding Hindi translation. The reordered English code ensures syntactic adherence to the target language's structure, while the translated code provides an accurate representation in the chosen language. Simultaneously, the Hindi translation enriches the understanding of the codebase for developers proficient in Hindi. This triad of outputs caters to diverse linguistic preferences and fosters effective collaboration in a multilingual development environment.
  ❖	Output File Writing:
    To document and organize key insights, our solution writes extracted information, including variables, data types, User-Defined Types (UDTs), and function names, to an output file. This structured file serves as a valuable reference for developers, offering a clear overview of the code's composition. By systematically recording these elements, the solution enhances code documentation, aiding developers in comprehending and navigating the intricacies of multilingualism codebases.

Implementation Details
1.	Text Extraction from PDF:
    ➢	Utilize Python libraries such as PyPDF2 or pdfplumber to extract text from PDF files.
    ➢	Implement a function that takes the path to the PDF file and the desired chapter range as input and outputs a text file containing all sentences from that chapter.
2.	Baseline Reordering Rules:
    ➢	Refer to Patel Raj Nath's reordering rules [1] and adapt them to the project's needs.
    ➢	Create a set of functions or scripts to apply these rules during the translation process, ensuring that the baseline reordering aligns with the specific characteristics of programming literature.
3.	Regular Expressions for Technical Elements:
    ➢	Develop regular expressions to identify and tag technical elements within the text, such as:
        ○	Assigned variables
        (e.g., using regex to match variable assignments like "x = 10").
        ○	Declared variables
        (e.g., identifying variable declarations like "int count;").
        ○	Data types
        (e.g., recognizing data type declarations like "float value;").
        ○	User-defined types
        (e.g., identifying structures or classes like "struct Point { int x, y; };").
        ○	Function names
        (e.g., using regex to match function declarations like "void printMessage();").
   ➢	Ensure that these elements are appropriately marked for preservation during the translation process.
4.	Pre and Post-Processing:
    ➢	Preprocessing:
      ○	Implement	a	preprocessing	module	to	clean	and	prepare	the	text	for translation.
      ○ Remove unnecessary formatting, special characters, or artifacts introduced during the PDF extraction.
      ○	Organize the text into sentences or segments for efficient translation.
    ➢	Postprocessing:
      ○	Develop a postprocessing module to refine the translated output.
      ○	Address any challenges introduced by code snippets or technical content.
      ○	Ensure	that	the	translated	sentences	maintain	technical	accuracy	and readability.
    ➢	Perform any necessary adjustments based on the specifics of the programming language used in the literature.
By implementing these detailed steps, the project aims to create a robust and effective system for translating programming literature into Indian Sign Language while preserving the technical nuances essential for accurate comprehension.

Testing Plan
❖	Quick Translation:
    a. User Interface:
      -	Ensure the "Quick Translation" page opens successfully with the input box and translate button.
      -	Verify that the user can input sentences, including C code with keywords and identifiers.
    b. Translation Accuracy:
      -	Test the translation functionality by inputting various sentences in different languages.
      -	Specifically, check that C keywords and identifiers are preserved accurately.
    c. Output Verification:
      - Confirm that the translated sentences are displayed correctly. - Check for the presence of three outputs: reordered sentence, ISL sentence, and Hindi sentence.
❖	File Translation:
    a. User Interface:
      -	Ensure the "File Translation" option is accessible from the homepage.
      -	Verify that the user can upload a text file successfully.
    b. File Conversion:
      -	Upload different types of text files, including those with C code, to ensure successful conversion.
      -	Confirm that the system preserves C keywords and identifiers during the file translation.
    c. Output File Download:
      - Verify that the user can download the converted text file after translation.
