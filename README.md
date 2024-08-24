<h1>Overview</h1>
    <p>This code is a Streamlit-based web application designed for Document Question Answering (Doc QA). The app allows users to upload a PDF document, select a pre-trained model, and ask questions related to the document. The app then processes the document and returns answers based on the selected model. Additionally, it can highlight the relevant sections of the document in the PDF file and display them as images.</p>
    
    <h2>Part 1: User Interface and Main Functionality</h2>

    <h3>Imports and Dependencies</h3>
    <p>The code imports various libraries including Streamlit, document processing utilities (docuploader), a question-answering module (qa), and several other libraries for handling files, images, and text processing.</p>

    <h3>Setup UI Function</h3>
    <p><strong>setup_ui():</strong> Sets up the page configuration for the Streamlit application, such as the page title.</p>

    <h3>Main Function</h3>
    <p><strong>main():</strong> The primary function that drives the application. It initializes session states, sets up the sidebar, handles document uploads, and processes the user's questions using the selected QA model.</p>

    <h3>Sidebar</h3>
    <p>The sidebar contains a description of the app, a dropdown for selecting the QA model, and an upload section for PDF files.</p>

    <h3>Main Area</h3>
    <p>Displays the uploaded PDF file, provides an input box for typing questions, and handles the question-answering process when the user clicks the "Submit" button. The results are displayed along with the option to view highlighted sections of the PDF.</p>
    
    <h2>Part 2: File Handling and PDF Processing</h2>

    <h3>Storage Class</h3>
    <p><strong>Storage:</strong> A class providing methods to list and retrieve files stored on the server. It's used for file selection in the app.</p>

    <h3>Extract Content Function</h3>
    <p><strong>extract_content_from_uploaded_file(file_content, file_type):</strong> Extracts text from a PDF file and returns it as a string.</p>

    <h3>Upload or Select Document Function</h3>
    <p><strong>upload_or_select_document(tab):</strong> Manages file uploads and file selection. It either uploads a new PDF document or allows the user to select a pre-existing document from a list.</p>

    <h3>Display PDF Function</h3>
    <p><strong>displayPDF(file):</strong> Displays the uploaded PDF file within the Streamlit app by embedding it as an HTML iframe.</p>

    <h3>Get Question List Function</h3>
    <p><strong>get_question_list(uploaded_file_name, selected_model):</strong> Extracts a list of questions from a CSV file that match the uploaded document name and the selected model.</p>

    <h3>Get Highlighted Image Function</h3>
    <p><strong>get_highlighted_image(pdf_path, search_sentence, answer):</strong> Generates images from the PDF with highlighted sections that match the search sentence and answer. It returns a list of images with highlighted areas.</p>
    
    <h2>Part 3: Question Answering and Results Display</h2>

    <h3>Get Answer Function</h3>
    <p><strong>get_answer(context, question, selected_model):</strong> Uses the selected model to answer a question based on the provided context. It loads the appropriate pre-trained model and tokenizer from Hugging Face's transformers library, processes the question, and returns the answer along with the surrounding text from the context.</p>

    <h3>Display Results Function</h3>
    <p><strong>display_results(top_answer, question, confidence=None):</strong> Displays the results of the QA process, including the answer and optionally, the model's confidence in its answer. If the answer is found, it is shown in a success message; otherwise, an error message is displayed.</p>
    
    <h2>Functionality Summary</h2>
    <p>
        <strong>Document Upload/Selection:</strong> Users can either upload a new PDF document or select an existing one.<br>
        <strong>Model Selection:</strong> Users choose from pre-trained QA models to process the document.<br>
        <strong>Question Answering:</strong> The app extracts answers from the document using the selected model.<br>
        <strong>Result Display:</strong> The app displays the answer and optionally highlights the relevant sections in the PDF.<br>
        <strong>PDF Handling:</strong> The app can display the PDF in the browser and highlight text within the PDF.
    </p>
    <p>This app provides an intuitive interface for users to interact with documents, allowing them to extract specific information efficiently using advanced NLP models.</p
