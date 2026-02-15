# Requirements Document: AskShruti! Voice Assistant

## Introduction

AskShruti! is a conversational AI voice assistant designed to help patients complete eSanjeevani case-intake forms through natural voice conversations in their native language. The system addresses digital literacy barriers by transforming complex medical form-filling into simple spoken interactions, making healthcare more accessible to elderly patients, citizens with low digital literacy, and anyone who prefers voice interaction over traditional form-filling.

## Glossary

- **AskShruti** - The AI voice assistant system
- **eSanjeevani** - India's telemedicine platform requiring case-intake forms
- **Patient** - The end user interacting with the voice assistant
- **Case_Intake_Form** - The digital form on eSanjeevani that captures patient medical information
- **Clinical_Entity** - Medical information extracted from patient speech (symptoms, history, medications, allergies)
- **Transcription_Engine** - The speech-to-text component that converts voice to text
- **Entity_Extractor** - The AI component that identifies and extracts clinical entities from transcribed text
- **Form_Mapper** - The component that maps extracted entities to form fields
- **Chatbot_UI** - The user interface component for voice interaction
- **Vernacular_Language** - Indian regional languages (Hindi, English, and others)

## Requirements

### Requirement 1: Voice Conversation Interface

**User Story:** As a patient, I want to interact with AskShruti through voice in my native language, so that I can provide my medical information without typing or reading complex forms.

#### Acceptance Criteria

1. WHEN a patient clicks the AskShruti chatbot icon, THE Chatbot_UI SHALL display a conversation interface with voice input capability
2. WHEN the conversation interface opens, THE AskShruti SHALL greet the patient and prompt for language selection
3. WHEN a patient selects a language, THE AskShruti SHALL conduct all subsequent interactions in that language
4. WHEN a patient speaks, THE Transcription_Engine SHALL convert the speech to text in the selected vernacular language
5. WHEN transcription completes, THE AskShruti SHALL provide visual feedback showing the transcribed text
6. WHEN a patient pauses speaking, THE AskShruti SHALL acknowledge receipt and prompt for additional information if needed

### Requirement 2: Multi-Language Support

**User Story:** As a patient who speaks Hindi or English, I want to communicate in my preferred language, so that I can express my health concerns naturally and accurately.

#### Acceptance Criteria

1. THE AskShruti SHALL support Hindi and English as initial languages
2. WHEN a patient selects a language, THE Transcription_Engine SHALL use language-specific speech recognition models
3. WHEN processing patient input, THE Entity_Extractor SHALL understand medical terminology in the selected language
4. WHEN displaying responses, THE AskShruti SHALL present all prompts and confirmations in the selected language
5. WHERE additional vernacular languages are configured, THE AskShruti SHALL make them available in the language selection menu

### Requirement 3: Clinical Entity Extraction

**User Story:** As a patient, I want the system to understand my medical narrative and extract relevant information, so that I don't have to manually fill individual form fields.

#### Acceptance Criteria

1. WHEN a patient describes symptoms, THE Entity_Extractor SHALL identify and extract symptom entities from the transcribed text
2. WHEN a patient mentions medical history, THE Entity_Extractor SHALL identify and extract historical medical conditions
3. WHEN a patient lists medications, THE Entity_Extractor SHALL identify and extract medication names and dosages
4. WHEN a patient mentions allergies, THE Entity_Extractor SHALL identify and extract allergy information
5. WHEN extraction completes, THE Entity_Extractor SHALL categorize each entity by type (symptom, history, medication, allergy)
6. IF ambiguous or unclear information is detected, THEN THE AskShruti SHALL ask clarifying questions to the patient

### Requirement 4: Automatic Form Population

**User Story:** As a patient, I want the system to automatically fill the eSanjeevani form with information from my conversation, so that I can save time and avoid manual data entry.

#### Acceptance Criteria

1. WHEN clinical entities are extracted, THE Form_Mapper SHALL map each entity to the corresponding Case_Intake_Form field
2. WHEN a form field has a matching entity, THE Form_Mapper SHALL populate that field with the extracted value
3. WHEN multiple entities map to the same field, THE Form_Mapper SHALL combine them appropriately
4. WHEN form population completes, THE AskShruti SHALL display the populated form to the patient
5. THE Form_Mapper SHALL preserve the original form structure and validation rules of the Case_Intake_Form

### Requirement 5: Patient Verification and Review

**User Story:** As a patient, I want to review and verify the auto-populated form before submission, so that I can ensure all information is accurate and complete.

#### Acceptance Criteria

1. WHEN the form is populated, THE AskShruti SHALL present a review screen showing all extracted and mapped information
2. WHEN displaying the review screen, THE AskShruti SHALL highlight which fields were auto-populated
3. WHEN a patient identifies an error, THE AskShruti SHALL allow the patient to correct the information through voice or manual editing
4. WHEN a patient confirms accuracy, THE AskShruti SHALL enable the save and proceed action
5. THE AskShruti SHALL prevent form submission until the patient explicitly confirms the information is correct

### Requirement 6: Chatbot UI Integration

**User Story:** As a patient on the eSanjeevani platform, I want easy access to AskShruti from the case creation page, so that I can quickly start a voice conversation.

#### Acceptance Criteria

1. WHEN a patient visits the eSanjeevani "Create Case" page, THE Chatbot_UI SHALL display an AskShruti icon in the bottom right corner
2. WHEN a patient clicks the chatbot icon, THE Chatbot_UI SHALL expand to show the conversation interface
3. WHEN the conversation interface is open, THE Chatbot_UI SHALL remain accessible and not obstruct the form
4. WHEN a patient closes the chatbot, THE Chatbot_UI SHALL minimize to the icon while preserving conversation state
5. THE Chatbot_UI SHALL provide clear visual indicators for microphone status (listening, processing, idle)

### Requirement 7: Transcription Accuracy and Feedback

**User Story:** As a patient, I want to see what the system understood from my speech, so that I can verify accuracy and correct any misunderstandings immediately.

#### Acceptance Criteria

1. WHEN speech is transcribed, THE AskShruti SHALL display the transcribed text in real-time or near real-time
2. WHEN transcription contains low-confidence segments, THE AskShruti SHALL highlight those segments for patient review
3. WHEN a patient identifies a transcription error, THE AskShruti SHALL allow the patient to re-speak or manually correct the text
4. THE Transcription_Engine SHALL achieve a minimum accuracy threshold appropriate for medical conversations
5. WHEN background noise affects transcription quality, THE AskShruti SHALL notify the patient and suggest a quieter environment

### Requirement 8: Conversation Flow Management

**User Story:** As a patient, I want the conversation to feel natural and guided, so that I know what information to provide and when.

#### Acceptance Criteria

1. WHEN the conversation starts, THE AskShruti SHALL explain the process and what information is needed
2. WHEN a patient finishes describing one topic, THE AskShruti SHALL prompt for the next relevant topic (symptoms → history → medications → allergies)
3. WHEN a patient provides incomplete information, THE AskShruti SHALL ask follow-up questions to gather missing details
4. WHEN all required information is collected, THE AskShruti SHALL summarize what was captured and proceed to review
5. THE AskShruti SHALL allow patients to skip optional sections or return to previous topics

### Requirement 9: Error Handling and Recovery

**User Story:** As a patient, I want the system to handle technical issues gracefully, so that I can complete my form even if problems occur.

#### Acceptance Criteria

1. IF the Transcription_Engine fails, THEN THE AskShruti SHALL notify the patient and offer to retry or switch to manual input
2. IF the Entity_Extractor fails, THEN THE AskShruti SHALL preserve the transcribed text and allow manual form filling
3. IF network connectivity is lost, THEN THE AskShruti SHALL save the conversation state locally and resume when connectivity returns
4. WHEN an error occurs, THE AskShruti SHALL provide clear error messages in the patient's selected language
5. THE AskShruti SHALL log all errors for system monitoring and improvement

### Requirement 10: Performance and Efficiency

**User Story:** As a patient, I want the voice assistant to respond quickly, so that I can complete my form in approximately 30 seconds as intended.

#### Acceptance Criteria

1. WHEN a patient speaks, THE Transcription_Engine SHALL begin processing within 500 milliseconds of speech completion
2. WHEN transcription completes, THE Entity_Extractor SHALL process the text within 2 seconds
3. WHEN entities are extracted, THE Form_Mapper SHALL populate the form within 1 second
4. THE AskShruti SHALL complete the entire flow (greeting to review) in under 60 seconds for typical cases
5. THE AskShruti SHALL provide progress indicators during processing to maintain patient engagement

### Requirement 11: Data Privacy and Security

**User Story:** As a patient, I want my medical information to be handled securely, so that my privacy is protected throughout the voice interaction.

#### Acceptance Criteria

1. WHEN voice data is captured, THE AskShruti SHALL encrypt the audio during transmission
2. WHEN transcription completes, THE AskShruti SHALL delete the audio recording unless explicitly saved for quality purposes
3. WHEN clinical entities are extracted, THE AskShruti SHALL handle all data according to healthcare privacy regulations
4. THE AskShruti SHALL not store patient conversations beyond the session unless required for medical records
5. WHEN integrating with eSanjeevani, THE AskShruti SHALL use secure authentication and authorization mechanisms

### Requirement 12: Accessibility Features

**User Story:** As an elderly patient or someone with disabilities, I want the interface to be accessible and easy to use, so that I can interact with the system independently.

#### Acceptance Criteria

1. THE Chatbot_UI SHALL use large, high-contrast buttons and text for visibility
2. THE Chatbot_UI SHALL provide audio feedback for all actions (button clicks, processing states)
3. WHEN displaying text, THE AskShruti SHALL use clear, simple language appropriate for low-literacy users
4. THE Chatbot_UI SHALL support touch and click interactions with large target areas
5. WHERE screen readers are detected, THE Chatbot_UI SHALL provide compatible markup and navigation

