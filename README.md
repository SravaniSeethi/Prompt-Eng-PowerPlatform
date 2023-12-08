# Power Platform for Prompt Engineering

Welcome to the Power Platform for Prompt Engineering repository! This repository focuses on exploring prompt creation techniques for GPT models and demonstrates an AI-powered healthcare solution leveraging Power Platform.

## Understanding Parts of a Prompt

In the realm of GPT models, a prompt comprises two crucial parts: the 'instruction' and the 'context.' This repository explains the significance of these components in directing AI responses:

### Characteristics of an Effective Prompt

- **Clear & Concise:** Crafted in easily understandable language.
- **Specific:** Offers precise guidance to steer GPT models.
- **Contextual & Relevant:** Provides ample context for generating meaningful output.

## Getting Started / Pre-requisites

To get started with this solution, ensure you have the prerequisites set up:

- Your Power Platform environment in the United States.
- Allow-listed tenant (during private preview).
- Power Apps or Power Automate license.
- Dataverse database installed in your environment.
- AI Builder add-on.

## Usage

Follow these steps to import this solution:

1. **Download the Unmanaged PowerApps Solution:** Download the zip file from the repo named [PromptEngineeringHealthCare_1_0_0_2.zip](PromptEngineeringHealthCare_1_0_0_2.zip)
2. **Import Solution to your environment:** Sign in to Power Apps, navigate to the right environment. Go to Solutions > Import Solution > Select the downloaded file from Step 1.
3. **Publish all customizations:** Once the import process is complete, click on "Publish all customizations".
4. **Add Sample Data:** Download the csv file named [SampleData.csv](SampleData.csv) from the repo and add to your Dataverse table > Add sample values into the "Name" column.

## Steps to Create an AI Healthcare Solution from scratch

1. **Creating Custom Prompts:** Utilize Power Apps to craft tailored instructions for medical instrument usage.
  Sign in to Power Apps. On the left navigation panel, select AI Hub > AI Prompts  > Crete text using custom prompts
  ![Power Platform AI Prompt](https://github.com/SravaniSeethi/Prompt-Eng-PowerPlatform/blob/66ececeb44c8e236a5390d999c1875a2e65f2f90/images/Power%20Platform%20AI%20Prompt.jpg)
  There are many types of prompts to pick from, I used the "Custom task with custom prompts".

  Building the prompt:
  
  Context: "I am a nurse at a children's hospital that needs to instructions on how to use this medical instrument:" I added a dynamic value "Medical Instrument" for the user to select (on the PowerApp).
  
  Instruction: "Provide a concise list of instructions to help me use the instrument appropriately. Do not add any additional text."
  
  Finished Prompt: 
  
  ```I am a nurse at a children's hospital that needs to instructions on how to use this medical instrument: Medical Instrument . Provide a concise list of instructions to help me use the instrument appropriately. Do not add any additional text.```
  
  ![Creating a Dynamic Prompt](https://github.com/SravaniSeethi/Prompt-Eng-PowerPlatform/blob/a01644ed72c6512882711785b0249000580daa5f/images/Creating%20a%20Dynamic%20Prompt.jpg)

2. **Dataverse Table Setup:** Establish a structured database for medical devices.

3. **Canvas PowerApp Development:** Develop a user-friendly app to retrieve and display prompt-generated instructions.

    i. Create a blank canvas powerapp, with a simple header. 

    ii. Add the Dataverse table and your prompt as the datasources

    iii. Add a gallery to show all medical devices from the Dataverse table and a text field to show the generated text from the prompt.

    iv. Add the following PowerFx formula for the 'OnSelect' property of the gallery: 

    ```Set(varInstructions, 'Medical Instrument Instructions'.Predict(ThisItem.Name))```

   v. Add a text label on the right half and the 'Text' property set to:

   ```varInstructions.Text```
   
  ![Canvas PowerApp Fx](https://github.com/SravaniSeethi/Prompt-Eng-PowerPlatform/blob/a01644ed72c6512882711785b0249000580daa5f/images/Canvas%20PowerApp%20Fx.jpg)
  
## Demo

Demonstration of the Canvas app to better visualize the functionality.

 ![Demo](https://github.com/SravaniSeethi/Prompt-Eng-PowerPlatform/blob/4f5f1fc649f9ef23b7a40a70d6d01cdde2f4d580/images/PromptEng.gif)

## Contributing

Contributions are welcomed! Feel free to fork this repository, make improvements, and submit a pull request.

## License

This project is licensed under [License Name] - see the [LICENSE](LICENSE) file for details.

---

Feel free to clone this repository to kickstart your exploration into prompt engineering and AI-powered healthcare solutions using the Power Platform!
