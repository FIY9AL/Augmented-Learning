// Library imports
using System.Collections.Generic;
using UnityEngine;
using Vuforia;
using TMPro;
using System;
using System.Linq;
// Variables Declareation
public class Math_Script : MonoBehaviour
{
    // Buttons Declareation
    public VirtualButtonBehaviour Next_Button, 
        Left_Rectangle_Button, Right_Rectangle_Button, 
        Up_Left_Button, Up_Right_Button, Down_Left_Button, Down_Right_Button,
        Left_Button, Right_Button, Home_Button, Retry_Button;
    // Texts Declareation
    public TextMeshPro Up_Title_Text, 
        Middle_Title_Text, Down_Title_Text, Question_Title_Text, Time_Title_Text,
        Score_Title_Text, Left_Rectangle_Text, Right_Rectangle_Text, Emoji_Text,
        Info_Text, Next_Text, Up_Left_Button_Text, Up_Right_Button_Text,
        Down_Left_Button_Text, Down_Right_Button_Text, Left_Button_Text,
        Right_Button_Text, Circle_Text, Correct_Wrong_Text, Quiz_Result_Text, 
        Words_ObjectName_Text, Home_Text, Retry_Text, Game_Path_Text;
    // Objects Declareation
    public GameObject Main_Background, 
        Next_Plane, Left_Rectangle_Plane, Right_Rectangle_Plane, Info_Plane,
        Up_Left_Button_Plane, Up_Right_Button_Plane, Down_Left_Button_Plane,
        Down_Right_Button_Plane, Left_Button_Plane, Right_Button_Plane, Circle_Plane,
        Home_Plane, Retry_Plane, Book1_3D, Cube_3D, Cube123_3D, CubeABC_3D, Cube123_3D_Focused,
        CubeABC_3D_Focused, Clock_3D, Book2_3D, Clock_3D_Focused, Book2_3D_Focused,
        Number_0_3D_Learn, Number_1_3D_Learn, Number_2_3D_Learn, Number_3_3D_Learn,
        Number_4_3D_Learn, Number_5_3D_Learn, Number_6_3D_Learn, Number_7_3D_Learn,
        Number_8_3D_Learn, Number_9_3D_Learn, Number_0_3D_Result1, Number_1_3D_Result1,
        Number_2_3D_Result1, Number_3_3D_Result1, Number_4_3D_Result1, Number_5_3D_Result1,
        Number_6_3D_Result1, Number_7_3D_Result1, Number_8_3D_Result1, Number_9_3D_Result1,
        Number_0_3D_Result2, Number_1_3D_Result2, Number_2_3D_Result2, Number_3_3D_Result2,
        Number_4_3D_Result2, Number_5_3D_Result2, Number_6_3D_Result2, Number_7_3D_Result2,
        Number_8_3D_Result2, Number_9_3D_Result2, Number_0_3D_Quiz1, Number_1_3D_Quiz1,
        Number_2_3D_Quiz1, Number_3_3D_Quiz1, Number_4_3D_Quiz1, Number_5_3D_Quiz1, Number_6_3D_Quiz1,
        Number_7_3D_Quiz1, Number_8_3D_Quiz1, Number_9_3D_Quiz1, Number_0_3D_Quiz2, Number_1_3D_Quiz2,
        Number_2_3D_Quiz2, Number_3_3D_Quiz2, Number_4_3D_Quiz2, Number_5_3D_Quiz2, Number_6_3D_Quiz2,
        Number_7_3D_Quiz2, Number_8_3D_Quiz2, Number_9_3D_Quiz2, Addition_3D, Addition_3D_Result,
        Addition_3D_Quiz, Substraction_3D, Substraction_3D_Result, Substraction_3D_Quiz, Division_3D,
        Division_3D_Result, Division_3D_Quiz, Multiplication_3D, Multiplication_3D_Result, Multiplication_3D_Quiz,
        Checkmark_3D, Crossmark_3D, Letter_A_3D, Letter_B_3D, Letter_C_3D, Letter_D_3D, Letter_E_3D, Letter_F_3D,
        Letter_G_3D, Letter_H_3D, Letter_I_3D, Letter_J_3D, Letter_K_3D, Letter_L_3D, Letter_M_3D, Letter_N_3D,
        Letter_O_3D, Letter_P_3D, Letter_Q_3D, Letter_R_3D, Letter_S_3D, Letter_T_3D, Letter_U_3D, Letter_V_3D,
        Letter_W_3D, Letter_X_3D, Letter_Y_3D, Letter_Z_3D, Apple_3D, Ball_3D, Cat_3D, Dog_3D, Earth_3D, Flag_3D,
        Grass_3D, Headphones_3D, IceCream_3D, Jewel_3D, Key_3D, Lion_3D, Mail_3D, Note_3D, Orange_3D, Plane_3D,
        Queen_3D, Rose_3D, Strawberry_3D, Turtle_3D, Umbrella_3D, Virus_3D, Watermelon_3D, Xylophone_3D, Yacht_3D, Zebra_3D;
    // Textures Declareation
    public Texture2D Normal_Ractangle_Texture,
        Focused_Ractangle_Texture, Normal_90dgree_Texture, Focused_90dgree_Texture, Normal_270dgree_Texture, Focused_270dgree_Texture;
    // Integers Declareation
    private int pageIndex, firstNumber, secondNumber, myOperatorArrayIndex,
        result_learn, quiz_questionIndex, quiz_firstNumber, quiz_secondNumber,
        quiz_answer1, quiz_answer2, quiz_answer3, quiz_answer4, quiz_score, myLetterArrayIndex = 0;
    // Array of english words declareation
    private readonly string[,] Words_Array = {
        {"A", "Apple_3D", "Apple", "Kiwi"},
        {"B", "Ball_3D", "Ball", "Wheel"},
        {"C", "Cat_3D", "Cat", "Lion"},
        {"D", "Dog_3D", "Dog", "Tiger"},
        {"E", "Earth_3D", "Earth", "Light"},
        {"F", "Flag_3D", "Flag", "Bike"},
        {"G", "Grass_3D", "Grass", "Water"},
        {"H", "Headphones_3D", "Headset", "Keyboard"},
        {"I", "IceCream_3D", "Ice Cream", "Juice"},
        {"J", "Jewel_3D", "Jewel", "Ring"},
        {"K", "Key_3D", "Key", "Remote"},
        {"L", "Lion_3D", "Lion", "Monkey"},
        {"M", "Mail_3D", "Mail", "Pen"},
        {"N", "Note_3D", "Note", "Mouse"},
        {"O", "Orange_3D", "Orange", "Melon"},
        {"P", "Plane_3D", "Plane", "Car"},
        {"Q", "Queen_3D", "Queen", "Shoes"},
        {"R", "Rose_3D", "Rose", "Tree"},
        {"S", "Strawberry_3D", "Strawberry", "Banana"},
        {"T", "Turtle_3D", "Turtle", "Zebra"},
        {"U", "Umbrella_3D", "Umbrella", "Paddle"},
        {"V", "Virus_3D", "Virus", "Planet"},
        {"W", "Watermelon_3D", "Watermelon", "Grapes"},
        {"X", "Xylophone_3D", "Xylophone", "Piano"},
        {"Y", "Yacht_3D", "Yacht", "Scooter"},
        {"Z", "Zebra_3D", "Zebra", "Giraffe"},
    };
    // Private variables to support functions
    private string[] myOperatorArray = { "Addition", "Substraction", "Division", "Multiplication" };
    private string quiz_operatorSign, myLetter = "";
    private string selectedSubject, selectedType, quiz_userAnswer, quiz_wordsAnswer1, quiz_wordsAnswer2 = null;
    private bool timerIsRunning1, timerIsRunning2, timerIsRunning3, myRetryHomeBool = false;
    private string[] quiz_buttonsTextArray = new string[4];
    private int[] quiz_WordsQuestionsIndexes = new int[10];
    private bool quiz_nextQuestion = true;
    private float timeRemaining1 = 3;
    private float timeRemaining2 = 1;
    private float timeRemaining3 = 100;
    // Private variables for accessing variables by string name
    private GameObject my3Dobject; 
    private TextMeshPro myTextObject;

    public void GamePathTextChanger() // Game path text handler
    {
        if (selectedSubject == null && selectedType == null) Game_Path_Text.text = "New Game";
        else Game_Path_Text.text = selectedSubject + " " + selectedType;
    }
    public void QuestionOrderHandler()
    {
        if (selectedSubject == "Math") // Math quiz questions order by operator
        {
            if (quiz_nextQuestion)
            {
                if (quiz_questionIndex == 1) GenerateMathQuestion_Addition(); // 1st question is addition
                else if (quiz_questionIndex == 2) GenerateMathQuestion_Substraction(); // 2nd question is substraction
                else if (quiz_questionIndex == 3) GenerateMathQuestion_Addition(); // 3rd question is addition
                else if (quiz_questionIndex == 4) GenerateMathQuestion_Substraction(); // 4th question is substraction
                else if (quiz_questionIndex == 5) GenerateMathQuestion_Multiplication(); // 5th question is multiplication
                else if (quiz_questionIndex == 6) GenerateMathQuestion_Division(); // 6th question is division
                else if (quiz_questionIndex == 7) GenerateMathQuestion_Multiplication(); // 7th question is multiplication
                else if (quiz_questionIndex == 8) GenerateMathQuestion_Division(); // 8th question is division
                else if (quiz_questionIndex == 9) GenerateMathQuestion_Multiplication(); // 9th question is multiplication
                else if (quiz_questionIndex == 10) GenerateMathQuestion_Division(); // 10th question is division
                QuizAnswersGenerator(); // Call function to generate random answers between boundries of real answer
                RandomQuizAnswersPlacementButton(); // Call function to random place the random answers in random buttons
            }
        }
        else if (selectedSubject == "Words") // Put random words quiz question answers on buttons
        {
            if (quiz_nextQuestion)
            {
                // Random place words quiz answers between two buttons
                System.Random rnd = new System.Random();
                int randomIndex = rnd.Next(2, 4);
                quiz_wordsAnswer1 = Words_Array[quiz_WordsQuestionsIndexes[quiz_questionIndex], randomIndex];
                if (randomIndex == 2) quiz_wordsAnswer2 = Words_Array[quiz_WordsQuestionsIndexes[quiz_questionIndex], 3];
                else quiz_wordsAnswer2 = Words_Array[quiz_WordsQuestionsIndexes[quiz_questionIndex], 2];
            }
        }
    }
    public void GenerateWordsQuestions() // Generate random words quiz question answers
    {
        int arraySize = 11, min = 0, max = 26;
        var items = new List<int>();
        for (var i = min; i < max; i++) items.Add(i);
        int[] choices = new int[arraySize];
        for (var i = 0; i < arraySize; i++)
        {
            var index = UnityEngine.Random.Range(0, items.Count);
            choices[i] = items[index];
            items.RemoveAt(index);
        }
        quiz_WordsQuestionsIndexes = choices;
    }
    public void GenerateMathQuestion_Addition() // Math quiz addidtion questions
    {
        System.Random rnd = new System.Random();
        quiz_firstNumber = rnd.Next(1, 10);
        quiz_secondNumber = rnd.Next(1, 10);
        quiz_operatorSign = "Addition";
    }
    public void GenerateMathQuestion_Substraction() // Math quiz susbtraction questions
    {
        do
        {
            System.Random rnd = new System.Random();
            quiz_firstNumber = rnd.Next(1, 10);
            quiz_secondNumber = rnd.Next(1, 10);
        } while (quiz_firstNumber <= quiz_secondNumber); // to make sure that second number is less than first number
        quiz_operatorSign = "Substraction";
    }
    public void GenerateMathQuestion_Division() // Math quiz division questions
    {
        do
        {
            System.Random rnd = new System.Random();
            quiz_firstNumber = rnd.Next(2, 10);
            quiz_secondNumber = quiz_firstNumber * rnd.Next(1, 10 / quiz_firstNumber);
        } while (quiz_firstNumber == quiz_secondNumber); // to make sure that second number is less than first number
        quiz_operatorSign = "Division";
        quiz_firstNumber += quiz_secondNumber;
        quiz_secondNumber = quiz_firstNumber - quiz_secondNumber;
        quiz_firstNumber -= quiz_secondNumber;
    }
    public void GenerateMathQuestion_Multiplication() // Math quiz mulitplication questions
    {
        System.Random rnd = new System.Random();
        quiz_firstNumber = rnd.Next(1, 10);
        quiz_secondNumber = rnd.Next(1, 10);
        quiz_operatorSign = "Multiplication";
    }
    public void QuizAnswersGenerator() // Make random question answers around the real answer
    {
        if (quiz_operatorSign == "Addition") quiz_answer1 = quiz_firstNumber + quiz_secondNumber;
        else if (quiz_operatorSign == "Substraction") quiz_answer1 = quiz_firstNumber - quiz_secondNumber;
        else if (quiz_operatorSign == "Division") quiz_answer1 = quiz_firstNumber / quiz_secondNumber;
        else if (quiz_operatorSign == "Multiplication") quiz_answer1 = quiz_firstNumber * quiz_secondNumber;
        System.Random rnd = new System.Random();
        do
        {
            quiz_answer2 = rnd.Next(quiz_answer1 - 3, quiz_answer1 + 4); // creates a number between answer -3 and answer +3
            quiz_answer3 = rnd.Next(quiz_answer1 - 3, quiz_answer1 + 4); // creates a number between answer -3 and answer +3
            quiz_answer4 = rnd.Next(quiz_answer1 - 3, quiz_answer1 + 4); // creates a number between answer -3 and answer +3
        } while (quiz_answer2 == quiz_answer3 || quiz_answer3 == quiz_answer4 || quiz_answer2 == quiz_answer4 || quiz_answer1 == quiz_answer2 || quiz_answer1 == quiz_answer3 || quiz_answer1 == quiz_answer4);
    } // The while loop is to make sure there is no identical answers
    public void HomeButtonListener(VirtualButtonBehaviour myButton) // Home button listener
    {
        // Each page has different operation when pressing the button
        if (pageIndex == 9)
        {
            selectedSubject = null; selectedType = null;
            PageLoader_2();
            firstNumber = 0; myOperatorArrayIndex = 0; secondNumber = 0;
        }
        else if (pageIndex == 16)
        {
            selectedSubject = null; selectedType = null; quiz_userAnswer = null;
            quiz_questionIndex = 0; quiz_firstNumber = 0; quiz_secondNumber = 0;
            timeRemaining3 = 100;
            quiz_operatorSign = "";
            quiz_answer1 = 0; quiz_answer2 = 0; quiz_answer3 = 0; quiz_answer4 = 0; quiz_score = 0;
            quiz_nextQuestion = true;
            quiz_buttonsTextArray = new string[4];
            PageLoader_2();
        }
        else if (pageIndex == 18)
        {
            selectedSubject = null; selectedType = null;
            my3Dobject = (GameObject)this.GetType().GetField("" + Words_Array[myLetterArrayIndex, 1]).GetValue(this); my3Dobject.SetActive(false);
            myLetter = "";
            myLetterArrayIndex = 0;
            Words_ObjectName_Text.text = " ";
            PageLoader_2();
        }
    }
    public void RetryButtonListener(VirtualButtonBehaviour myButton) // Retry button listener
    {
        if (selectedSubject == "Math") // When subject is math do the following
        {
            if (selectedType == "Quiz") // When type is quiz do the following
            {
                quiz_questionIndex = 0; quiz_firstNumber = 0; quiz_secondNumber = 0;
                quiz_answer1 = 0; quiz_answer2 = 0; quiz_answer3 = 0; quiz_answer4 = 0; quiz_score = 0;
                timeRemaining3 = 100;
                quiz_operatorSign = "";
                quiz_nextQuestion = true;
                quiz_buttonsTextArray = new string[4];
                PageLoader_10();
            }
            else if (selectedType == "Learn") // When type is learn do the following
            {
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Result1").GetValue(this); my3Dobject.SetActive(false);
                my3Dobject = (GameObject)this.GetType().GetField(myOperatorArray[myOperatorArrayIndex] + "_3D_Result").GetValue(this); my3Dobject.SetActive(false);
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Result2").GetValue(this); my3Dobject.SetActive(false);
                firstNumber = 0; myOperatorArrayIndex = 0; secondNumber = 0;
                PageLoader_6();
            }
        }
        else if (selectedSubject == "Words") // When subject is words do the following
        {
            if (selectedType == "Quiz") // When type is quiz do the following
            {
                quiz_questionIndex = 0; quiz_score = 0;
                timeRemaining3 = 100;
                quiz_nextQuestion = true;
                quiz_userAnswer = null;
                PageLoader_10();
            }
            else if (selectedType == "Learn") // When type is learn do the following
            {
                my3Dobject = (GameObject)this.GetType().GetField("" + Words_Array[myLetterArrayIndex, 1]).GetValue(this); my3Dobject.SetActive(false);
                myLetter = "";
                myLetterArrayIndex = 0;
                Words_ObjectName_Text.text = " ";
                PageLoader_17();
            }
        }
    }
    public void NextButtonListener(VirtualButtonBehaviour myButton) // Next button listener
    {
        // Each page has different operation when pressing the button
        if (pageIndex == 1) PageLoader_2();
        else if (pageIndex == 2) PageLoader_4();
        else if (pageIndex == 4)
        {
            if (selectedSubject == "Math")
            {
                if (selectedType == "Quiz") PageLoader_10();
                else if (selectedType == "Learn") PageLoader_6();
            }
            else if (selectedSubject == "Words")
            {
                if (selectedType == "Quiz") PageLoader_10();
                else if (selectedType == "Learn") PageLoader_17();
            }
        }
        else if (pageIndex == 6) PageLoader_7(); else if (pageIndex == 7) PageLoader_8(); else if (pageIndex == 8) PageLoader_9();
        else if (pageIndex == 10)
        {
            if (selectedSubject == "Math") PageLoader_11();
            else if (selectedSubject == "Words") PageLoader_19();
        }
        else if (pageIndex == 11)
        {
            PageLoader_13();
            quiz_buttonsTextArray = new string[4];
            quiz_questionIndex++;
            quiz_nextQuestion = true;
            if (Convert.ToInt32(quiz_userAnswer) == quiz_answer1) quiz_score++;
            quiz_userAnswer = null;
        }
        else if (pageIndex == 14 || pageIndex == 15) PageLoader_16(); else if (pageIndex == 17) PageLoader_18();
        else if (pageIndex == 19)
        {
            PageLoader_21();
            quiz_nextQuestion = true;
            if (quiz_userAnswer == Words_Array[quiz_WordsQuestionsIndexes[quiz_questionIndex], 2]) quiz_score++;
            quiz_userAnswer = null;
        }
    }
    public void LeftButtonListener(VirtualButtonBehaviour myButton) // Left button listener
    {
        if (pageIndex == 19)
        {
            Left_Button_Plane.GetComponent<Renderer>().material.mainTexture = Focused_90dgree_Texture;
            Right_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_270dgree_Texture;
            quiz_userAnswer = Left_Button_Text.GetParsedText();
            PageLoader_20();
        }
    }
    public void RightButtonListener(VirtualButtonBehaviour myButton) // Right button listener
    {
        if (pageIndex == 19)
        {
            Right_Button_Plane.GetComponent<Renderer>().material.mainTexture = Focused_270dgree_Texture;
            Left_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_90dgree_Texture;
            quiz_userAnswer = Right_Button_Text.GetParsedText();
            PageLoader_20();
        }
    }
    public void UpLeftButtonListener(VirtualButtonBehaviour myButton) // Up Lift button listener
    {
        // Each page has different operation when pressing the button
        if (pageIndex == 6)
        {
            if (firstNumber == 0)
            {
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(false);
                firstNumber = 9;
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(true);
            }
            else
            {
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(false);
                firstNumber -= 1;
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(true);
            }
        }
        else if (pageIndex == 7)
        {
            my3Dobject = (GameObject)this.GetType().GetField(myOperatorArray[myOperatorArrayIndex] + "_3D").GetValue(this); my3Dobject.SetActive(false);
            operatorArraySelection("decrease");
            my3Dobject = (GameObject)this.GetType().GetField(myOperatorArray[myOperatorArrayIndex] + "_3D").GetValue(this); my3Dobject.SetActive(true);
        }
        else if (pageIndex == 8)
        {
            if (secondNumber == 0)
            {
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(false);
                secondNumber = 9;
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(true);
            }
            else
            {
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(false);
                secondNumber -= 1;
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(true);
            }
        }
        else if (pageIndex == 11)
        {
            quiz_userAnswer = Up_Left_Button_Text.GetParsedText();
            PageLoader_12();
        }
        else if (pageIndex == 17)
        {
            if (myLetterArrayIndex == 0)
            {
                my3Dobject = (GameObject)this.GetType().GetField("Letter_" + myLetter + "_3D").GetValue(this); my3Dobject.SetActive(false);
                myLetterArrayIndex = 25;
                myLetter = Words_Array[myLetterArrayIndex, 0];
                my3Dobject = (GameObject)this.GetType().GetField("Letter_" + myLetter + "_3D").GetValue(this); my3Dobject.SetActive(true);
            }
            else
            {
                my3Dobject = (GameObject)this.GetType().GetField("Letter_" + myLetter + "_3D").GetValue(this); my3Dobject.SetActive(false);
                myLetterArrayIndex--;
                myLetter = Words_Array[myLetterArrayIndex, 0];
                my3Dobject = (GameObject)this.GetType().GetField("Letter_" + myLetter + "_3D").GetValue(this); my3Dobject.SetActive(true);
            }
        }
    }
    public void UpRightButtonListener(VirtualButtonBehaviour myButton) // Up right button listener
    {
        // Each page has different operation when pressing the button
        if (pageIndex == 6)
        {
            if (firstNumber == 9)
            {
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(false);
                firstNumber = 0;
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(true);
            }
            else
            {
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(false);
                firstNumber += 1;
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(true);
            }
        }
        else if (pageIndex == 7)
        {
            my3Dobject = (GameObject)this.GetType().GetField(myOperatorArray[myOperatorArrayIndex] + "_3D").GetValue(this); my3Dobject.SetActive(false);
            operatorArraySelection("increase");
            my3Dobject = (GameObject)this.GetType().GetField(myOperatorArray[myOperatorArrayIndex] + "_3D").GetValue(this); my3Dobject.SetActive(true);
        }
        else if (pageIndex == 8)
        {
            if (secondNumber == 9)
            {
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(false);
                secondNumber = 0;
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(true);
            }
            else
            {
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(false);
                secondNumber += 1;
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(true);
            }
        }
        else if (pageIndex == 11)
        {
            quiz_userAnswer = Up_Right_Button_Text.GetParsedText();
            PageLoader_12();
        }
        else if (pageIndex == 17)
        {
            if (myLetterArrayIndex == 25)
            {
                my3Dobject = (GameObject)this.GetType().GetField("Letter_" + myLetter + "_3D").GetValue(this); my3Dobject.SetActive(false);
                myLetterArrayIndex = 0;
                myLetter = Words_Array[myLetterArrayIndex, 0];
                my3Dobject = (GameObject)this.GetType().GetField("Letter_" + myLetter + "_3D").GetValue(this); my3Dobject.SetActive(true);
            }
            else
            {
                my3Dobject = (GameObject)this.GetType().GetField("Letter_" + myLetter + "_3D").GetValue(this); my3Dobject.SetActive(false);
                myLetterArrayIndex++;
                myLetter = Words_Array[myLetterArrayIndex, 0];
                my3Dobject = (GameObject)this.GetType().GetField("Letter_" + myLetter + "_3D").GetValue(this); my3Dobject.SetActive(true);
            }
        }
    }
    public void DownLeftButtonListener(VirtualButtonBehaviour myButton) // Down left button listener
    {
        if (pageIndex == 11)
        {
            quiz_userAnswer = Down_Left_Button_Text.GetParsedText();
            PageLoader_12();
        }
    }
    public void DownRightButtonListener(VirtualButtonBehaviour myButton) // Down right button listener
    {
        if (pageIndex == 11)
        {
            quiz_userAnswer = Down_Right_Button_Text.GetParsedText();
            PageLoader_12();
        }
    }
    public void LeftRectangleButtonListener(VirtualButtonBehaviour myButton) // Left rectangle button listener
    {
        // Each page has different operation when pressing the button
        if (pageIndex == 2)
        {
            selectedSubject = "Math";
            PageLoader_3();
        }
        else if (pageIndex == 4)
        {
            selectedType = "Quiz";
            PageLoader_5();
        }
    }
    public void RightRectangleButtonListener(VirtualButtonBehaviour myButton) // Right rectangle button listener
    {
        // Each page has different operation when pressing the button
        if (pageIndex == 2)
        {
            selectedSubject = "Words";
            PageLoader_3();
        }
        else if (pageIndex == 4)
        {
            selectedType = "Learn";
            PageLoader_5();
        }
    }
    public void EnableNextButton() // Enable next button after being faded out
    {
        // Each page has different operation when pressing the button
        if (pageIndex == 9) Next_Text.text = "Again";
        else if (pageIndex == 10) Next_Text.text = "Start";
        else if (pageIndex == 14 || pageIndex == 15) Next_Text.text = "Result";
        else if (pageIndex == 16 || pageIndex == 18) Next_Text.text = "Again";
        else
        {
            Next_Text.text = "Next";
        }
        Next_Button.enabled = true; Next_Plane.SetActive(true);
    }
    public void DisableNextButton() // Disable next button for amount of time
    {
        Next_Button.enabled = false; Next_Plane.SetActive(false); Next_Text.text = " ";
        timerIsRunning2 = true; timeRemaining2 = 1; //Start timer, Set time duration
    }
    public void EnableRetryHomeButton() // Enable retry, home buttons after being faded out
    {
        myRetryHomeBool = false; // For timer if condition
        Home_Button.enabled = true; Home_Plane.SetActive(true); Home_Text.text = "Home";
        Retry_Button.enabled = true; Retry_Plane.SetActive(true); Retry_Text.text = "Retry";
    }
    public void DisableRetryHomeButton() // Disable retry, home buttons for amount of time
    {
        myRetryHomeBool = true; // For timer if condition
        Home_Button.enabled = false; Home_Plane.SetActive(false); Home_Text.text = " ";
        Retry_Button.enabled = false; Retry_Plane.SetActive(false); Retry_Text.text = " ";
        timerIsRunning2 = true; timeRemaining2 = 1; //Start timer, Set time duration
    }
    public void operatorArraySelection(string myChoice) // To set boundries when selecting operators in math learning page
    {
        if (myChoice == "increase")
        {
            if (myOperatorArrayIndex == (myOperatorArray.Length) - 1) myOperatorArrayIndex = 0;
            else myOperatorArrayIndex++;
        }
        if (myChoice == "decrease")
        {
            if (myOperatorArrayIndex == 0) myOperatorArrayIndex = (myOperatorArray.Length) - 1;
            else myOperatorArrayIndex--;
        }
    }
    public void calculateLearnResult() // To display math learning equation result
    {
        if (myOperatorArray[myOperatorArrayIndex] == myOperatorArray[0]) result_learn = firstNumber + secondNumber;
        else if (myOperatorArray[myOperatorArrayIndex] == myOperatorArray[1]) result_learn = firstNumber - secondNumber;
        else if (myOperatorArray[myOperatorArrayIndex] == myOperatorArray[2])
        {
            if (secondNumber == 0) result_learn = 987654321; // When divison done by zero, set special number to identify later
            else result_learn = firstNumber / secondNumber;
        }
        else if (myOperatorArray[myOperatorArrayIndex] == myOperatorArray[3]) result_learn = firstNumber * secondNumber;
    }
    public void RandomQuizAnswersPlacementButton() // To random place questions answers on different buttons each question
    {
        string[] myButtonTextArray = { "Up_Left", "Up_Right", "Down_Left", "Down_Right" };
        System.Random rnd = new System.Random();
        int randomIndex = rnd.Next(0, myButtonTextArray.Length);
        myTextObject = (TextMeshPro)this.GetType().GetField(myButtonTextArray[randomIndex] + "_Button_Text").GetValue(this); myTextObject.text = Convert.ToString(quiz_answer1);
        int deleteIndex = Array.IndexOf(myButtonTextArray, myButtonTextArray[randomIndex]);
        myButtonTextArray = myButtonTextArray.Where((val, idx) => idx != deleteIndex).ToArray();
        rnd = new System.Random();
        randomIndex = rnd.Next(0, myButtonTextArray.Length);
        myTextObject = (TextMeshPro)this.GetType().GetField(myButtonTextArray[randomIndex] + "_Button_Text").GetValue(this); myTextObject.text = Convert.ToString(quiz_answer2);
        deleteIndex = Array.IndexOf(myButtonTextArray, myButtonTextArray[randomIndex]);
        myButtonTextArray = myButtonTextArray.Where((val, idx) => idx != deleteIndex).ToArray();
        rnd = new System.Random();
        randomIndex = rnd.Next(0, myButtonTextArray.Length);
        myTextObject = (TextMeshPro)this.GetType().GetField(myButtonTextArray[randomIndex] + "_Button_Text").GetValue(this); myTextObject.text = Convert.ToString(quiz_answer3);
        deleteIndex = Array.IndexOf(myButtonTextArray, myButtonTextArray[randomIndex]);
        myButtonTextArray = myButtonTextArray.Where((val, idx) => idx != deleteIndex).ToArray();
        rnd = new System.Random();
        randomIndex = rnd.Next(0, myButtonTextArray.Length);
        myTextObject = (TextMeshPro)this.GetType().GetField(myButtonTextArray[randomIndex] + "_Button_Text").GetValue(this); myTextObject.text = Convert.ToString(quiz_answer4);
        deleteIndex = Array.IndexOf(myButtonTextArray, myButtonTextArray[randomIndex]);
        myButtonTextArray = myButtonTextArray.Where((val, idx) => idx != deleteIndex).ToArray();
    }
    public void ButtonPlaneHandler(string theButton) // To change button plane color from normal to focused
    {
        Up_Left_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_90dgree_Texture;
        Up_Right_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_270dgree_Texture;
        Down_Left_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_90dgree_Texture;
        Down_Right_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_270dgree_Texture;
        if (theButton == "Up_Left") Up_Left_Button_Plane.GetComponent<Renderer>().material.mainTexture = Focused_90dgree_Texture;
        else if (theButton == "Up_Right") Up_Right_Button_Plane.GetComponent<Renderer>().material.mainTexture = Focused_270dgree_Texture;
        else if (theButton == "Down_Left") Down_Left_Button_Plane.GetComponent<Renderer>().material.mainTexture = Focused_90dgree_Texture;
        else if (theButton == "Down_Right") Down_Right_Button_Plane.GetComponent<Renderer>().material.mainTexture = Focused_270dgree_Texture;
    }
    public void PageLoader_1() // This function loads the gui elements of page number 1
    {
        DisableNextButton(); // To fade in the next button after few moments
        pageIndex = 1;
        Up_Title_Text.text = "Welcome to";
        Down_Title_Text.text = "Augmented Learning";
        Middle_Title_Text.text = " ";
        Emoji_Text.text = " ";
        Info_Text.text = " ";
        Question_Title_Text.text = " ";
        Time_Title_Text.text = " ";
        Score_Title_Text.text = " ";
        Correct_Wrong_Text.text = " ";
        Quiz_Result_Text.text = " ";
        Words_ObjectName_Text.text = " ";
        Left_Rectangle_Button.enabled = false; Left_Rectangle_Plane.SetActive(false); Left_Rectangle_Text.text = " ";
        Right_Rectangle_Button.enabled = false; Right_Rectangle_Plane.SetActive(false); Right_Rectangle_Text.text = " ";
        Up_Left_Button.enabled = false; Up_Left_Button_Plane.SetActive(false); Up_Left_Button_Text.text = " ";
        Up_Right_Button.enabled = false; Up_Right_Button_Plane.SetActive(false); Up_Right_Button_Text.text = " ";
        Down_Left_Button.enabled = false; Down_Left_Button_Plane.SetActive(false); Down_Left_Button_Text.text = " ";
        Down_Right_Button.enabled = false; Down_Right_Button_Plane.SetActive(false); Down_Right_Button_Text.text = " ";
        Left_Button.enabled = false; Left_Button_Plane.SetActive(false); Left_Button_Text.text = " ";
        Right_Button.enabled = false; Right_Button_Plane.SetActive(false); Right_Button_Text.text = " ";
        Home_Button.enabled = false; Home_Plane.SetActive(false); Home_Text.text = " ";
        Retry_Button.enabled = false; Retry_Plane.SetActive(false); Retry_Text.text = " ";
        Circle_Plane.SetActive(false); Circle_Text.text = " ";
    }
    public void PageLoader_2() // This function loads the gui elements of page number 2
    {
        pageIndex = 2;
        Up_Title_Text.text = " ";
        Middle_Title_Text.text = "Subject to play?";
        Down_Title_Text.text = " ";
        Info_Text.text = " ";
        Quiz_Result_Text.text = " ";
        Left_Rectangle_Button.enabled = true; Left_Rectangle_Plane.SetActive(true); Left_Rectangle_Text.text = "Math";
        Right_Rectangle_Button.enabled = true; Right_Rectangle_Plane.SetActive(true); Right_Rectangle_Text.text = "Words";
        Home_Button.enabled = false; Home_Plane.SetActive(false); Home_Text.text = " ";
        Retry_Button.enabled = false; Retry_Plane.SetActive(false); Retry_Text.text = " ";
        Circle_Plane.SetActive(false); Circle_Text.text = " ";
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Result1").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField(myOperatorArray[myOperatorArrayIndex] + "_3D_Result").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Result2").GetValue(this); my3Dobject.SetActive(false);
        if (selectedSubject != null) DisableNextButton();
        else
        {
            Next_Button.enabled = false; Next_Plane.SetActive(false); Next_Text.text = " ";
        }
        Info_Plane.SetActive(false); Cube_3D.SetActive(false); Book1_3D.SetActive(false);
        Cube123_3D.SetActive(true); CubeABC_3D.SetActive(true); CubeABC_3D_Focused.SetActive(false); Cube123_3D_Focused.SetActive(false);
        if (selectedSubject == "Math")
        {
            Left_Rectangle_Plane.GetComponent<Renderer>().material.mainTexture = Focused_Ractangle_Texture;
            Right_Rectangle_Plane.GetComponent<Renderer>().material.mainTexture = Normal_Ractangle_Texture;
        }
        else if (selectedSubject == "Words")
        {
            Right_Rectangle_Plane.GetComponent<Renderer>().material.mainTexture = Focused_Ractangle_Texture;
            Left_Rectangle_Plane.GetComponent<Renderer>().material.mainTexture = Normal_Ractangle_Texture;
        }
        else
        {
            Left_Rectangle_Plane.GetComponent<Renderer>().material.mainTexture = Normal_Ractangle_Texture;
            Right_Rectangle_Plane.GetComponent<Renderer>().material.mainTexture = Normal_Ractangle_Texture;
        }
    }
    public void PageLoader_3() // This function loads the gui elements of page number 3
    {
        pageIndex = 3;
        timerIsRunning2 = false; //Kill next button timer
        Cube123_3D.SetActive(false); CubeABC_3D.SetActive(false);
        Left_Rectangle_Button.enabled = false; Left_Rectangle_Plane.SetActive(false); Left_Rectangle_Text.text = " ";
        Right_Rectangle_Button.enabled = false; Right_Rectangle_Plane.SetActive(false); Right_Rectangle_Text.text = " ";
        Next_Button.enabled = false; Next_Plane.SetActive(false); Next_Text.text = " ";
        Info_Plane.SetActive(true);
        if (selectedSubject == "Math")
        {
            Cube123_3D_Focused.SetActive(true);
            Info_Text.text = selectedSubject;
        }
        else if (selectedSubject == "Words")
        {
            CubeABC_3D_Focused.SetActive(true);
            Info_Text.text = selectedSubject;
        }
        timerIsRunning1 = true; timeRemaining1 = 3; //Start timer, Set time duration
    }
    public void PageLoader_4() // This function loads the gui elements of page number 4
    {
        pageIndex = 4;
        Up_Title_Text.text = "Selected subject: " + selectedSubject;
        Middle_Title_Text.text = " ";
        Down_Title_Text.text = "Type to play?";
        Info_Text.text = " ";
        Left_Rectangle_Button.enabled = true; Left_Rectangle_Plane.SetActive(true); Left_Rectangle_Text.text = "Quiz";
        Right_Rectangle_Button.enabled = true; Right_Rectangle_Plane.SetActive(true); Right_Rectangle_Text.text = "Learn";
        if (selectedType != null) DisableNextButton();
        else
        {
            Next_Button.enabled = false; Next_Plane.SetActive(false); Next_Text.text = " ";
        }
        Info_Plane.SetActive(false); Cube123_3D.SetActive(false); CubeABC_3D.SetActive(false);
        Clock_3D.SetActive(true); Book2_3D.SetActive(true); Clock_3D_Focused.SetActive(false); Book2_3D_Focused.SetActive(false);
        if (selectedType == "Quiz")
        {
            Left_Rectangle_Plane.GetComponent<Renderer>().material.mainTexture = Focused_Ractangle_Texture;
            Right_Rectangle_Plane.GetComponent<Renderer>().material.mainTexture = Normal_Ractangle_Texture;
        }
        else if (selectedType == "Learn")
        {
            Right_Rectangle_Plane.GetComponent<Renderer>().material.mainTexture = Focused_Ractangle_Texture;
            Left_Rectangle_Plane.GetComponent<Renderer>().material.mainTexture = Normal_Ractangle_Texture;
        }
        else
        {
            Left_Rectangle_Plane.GetComponent<Renderer>().material.mainTexture = Normal_Ractangle_Texture;
            Right_Rectangle_Plane.GetComponent<Renderer>().material.mainTexture = Normal_Ractangle_Texture;
        }
    }
    public void PageLoader_5() // This function loads the gui elements of page number 5
    {
        pageIndex = 5;
        timerIsRunning2 = false; //Kill next button timer
        Clock_3D.SetActive(false); Book2_3D.SetActive(false); Info_Plane.SetActive(true);
        Left_Rectangle_Button.enabled = false; Left_Rectangle_Plane.SetActive(false); Left_Rectangle_Text.text = " ";
        Right_Rectangle_Button.enabled = false; Right_Rectangle_Plane.SetActive(false); Right_Rectangle_Text.text = " ";
        Next_Button.enabled = false; Next_Plane.SetActive(false); Next_Text.text = " ";
        if (selectedType == "Quiz")
        {
            Clock_3D_Focused.SetActive(true);
            Info_Text.text = selectedType;
        }
        else if (selectedType == "Learn")
        {
            Book2_3D_Focused.SetActive(true);
            Info_Text.text = selectedType;
        }
        timerIsRunning1 = true; timeRemaining1 = 3; //Start timer, Set time duration
    }
    public void PageLoader_6() // This function loads the gui elements of page number 6
    {
        DisableNextButton(); // To fade in the next button after few moments
        pageIndex = 6;
        Up_Title_Text.text = " ";
        Middle_Title_Text.text = "First number?";
        Down_Title_Text.text = " ";
        Left_Rectangle_Button.enabled = false; Left_Rectangle_Plane.SetActive(false); Left_Rectangle_Text.text = " ";
        Right_Rectangle_Button.enabled = false; Right_Rectangle_Plane.SetActive(false); Right_Rectangle_Text.text = " ";
        Home_Button.enabled = false; Home_Plane.SetActive(false); Home_Text.text = " ";
        Retry_Button.enabled = false; Retry_Plane.SetActive(false); Retry_Text.text = " ";
        Clock_3D.SetActive(false); Book2_3D.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(true);
        Up_Left_Button.enabled = true; Up_Left_Button_Plane.SetActive(true); Up_Left_Button_Text.text = "-";
        Up_Right_Button.enabled = true; Up_Right_Button_Plane.SetActive(true); Up_Right_Button_Text.text = "+";
        Circle_Plane.SetActive(false); Circle_Text.text = " ";
        Up_Left_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_90dgree_Texture;
        Up_Right_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_270dgree_Texture;
    }
    public void PageLoader_7() // This function loads the gui elements of page number 7
    {
        DisableNextButton(); // To fade in the next button after few moments
        pageIndex = 7;
        Middle_Title_Text.text = "Operator?";
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField(myOperatorArray[myOperatorArrayIndex] + "_3D").GetValue(this); my3Dobject.SetActive(true);
        Up_Left_Button_Text.text = "<";
        Up_Right_Button_Text.text = ">";
        Up_Left_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_90dgree_Texture;
        Up_Right_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_270dgree_Texture;
    }
    public void PageLoader_8() // This function loads the gui elements of page number 8
    {
        DisableNextButton(); // To fade in the next button after few moments
        pageIndex = 8;
        Middle_Title_Text.text = "Second number?";
        my3Dobject = (GameObject)this.GetType().GetField(myOperatorArray[myOperatorArrayIndex] + "_3D").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(true);
        Up_Left_Button_Text.text = "-";
        Up_Right_Button_Text.text = "+";
        Up_Left_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_90dgree_Texture;
        Up_Right_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_270dgree_Texture;
    }
    public void PageLoader_9() // This function loads the gui elements of page number 9
    {
        DisableRetryHomeButton(); // To fade in retry, home buttons after few moments
        pageIndex = 9;
        Middle_Title_Text.text = "Results";
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Learn").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + firstNumber + "_3D_Result1").GetValue(this); my3Dobject.SetActive(true);
        my3Dobject = (GameObject)this.GetType().GetField(myOperatorArray[myOperatorArrayIndex] + "_3D_Result").GetValue(this); my3Dobject.SetActive(true);
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + secondNumber + "_3D_Result2").GetValue(this); my3Dobject.SetActive(true);
        Up_Left_Button.enabled = false; Up_Left_Button_Plane.SetActive(false); Up_Left_Button_Text.text = " ";
        Up_Right_Button.enabled = false; Up_Right_Button_Plane.SetActive(false); Up_Right_Button_Text.text = " ";
        Next_Button.enabled = false; Next_Text.text = " "; Next_Plane.SetActive(false);
        Circle_Plane.SetActive(true);
        calculateLearnResult();
        if (result_learn == 987654321) Circle_Text.text = "Undefined"; // Divison by zero 
        else Circle_Text.text = Convert.ToString(result_learn);
    }
    public void PageLoader_10() // This function loads the gui elements of page number 10
    {
        DisableNextButton(); // To fade in the next button after few moments
        pageIndex = 10;
        Up_Title_Text.text = " ";
        Middle_Title_Text.text = "Ready?";
        Down_Title_Text.text = " ";
        Emoji_Text.text = "<sprite name=\"Emojis_5\">";
        Quiz_Result_Text.text = " ";
        Left_Rectangle_Button.enabled = false; Left_Rectangle_Plane.SetActive(false); Left_Rectangle_Text.text = " ";
        Right_Rectangle_Button.enabled = false; Right_Rectangle_Plane.SetActive(false); Right_Rectangle_Text.text = " ";
        Home_Button.enabled = false; Home_Plane.SetActive(false); Home_Text.text = " ";
        Retry_Button.enabled = false; Retry_Plane.SetActive(false); Retry_Text.text = " ";
        Clock_3D.SetActive(false); Book2_3D.SetActive(false);
    }
    public void PageLoader_11() // This function loads the gui elements of page number 11
    {
        pageIndex = 11;
        Up_Title_Text.text = "Question       Time          Score";
        Middle_Title_Text.text = " ";
        Down_Title_Text.text = " ";
        Emoji_Text.text = " ";
        Checkmark_3D.SetActive(false); Crossmark_3D.SetActive(false);
        Correct_Wrong_Text.text = " ";
        if (quiz_questionIndex != 0)
        {
            if (quiz_userAnswer == null)
            {
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_firstNumber + "_3D_Quiz1").GetValue(this); my3Dobject.SetActive(false);
                my3Dobject = (GameObject)this.GetType().GetField(quiz_operatorSign + "_3D_Quiz").GetValue(this); my3Dobject.SetActive(false);
                my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_secondNumber + "_3D_Quiz2").GetValue(this); my3Dobject.SetActive(false);
                ButtonPlaneHandler(null);
            }
        }
        if (quiz_questionIndex == 0)
        {
            quiz_questionIndex++;
            ButtonPlaneHandler(null);
        }
        QuestionOrderHandler();
        quiz_nextQuestion = false;
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_firstNumber + "_3D_Result1").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField(quiz_operatorSign + "_3D_Result").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_secondNumber + "_3D_Result2").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_firstNumber + "_3D_Quiz1").GetValue(this); my3Dobject.SetActive(true);
        my3Dobject = (GameObject)this.GetType().GetField(quiz_operatorSign + "_3D_Quiz").GetValue(this); my3Dobject.SetActive(true);
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_secondNumber + "_3D_Quiz2").GetValue(this); my3Dobject.SetActive(true);
        Up_Left_Button.enabled = true; Up_Left_Button_Plane.SetActive(true);
        Up_Right_Button.enabled = true; Up_Right_Button_Plane.SetActive(true);
        Down_Left_Button.enabled = true; Down_Left_Button_Plane.SetActive(true);
        Down_Right_Button.enabled = true; Down_Right_Button_Plane.SetActive(true);
        if (quiz_buttonsTextArray[0] != null)
        {
            Up_Left_Button_Text.text = quiz_buttonsTextArray[0];
            Up_Right_Button_Text.text = quiz_buttonsTextArray[1];
            Down_Left_Button_Text.text = quiz_buttonsTextArray[2];
            Down_Right_Button_Text.text = quiz_buttonsTextArray[3];
            if (quiz_buttonsTextArray[0] == quiz_userAnswer) ButtonPlaneHandler("Up_Left");
            else if (quiz_buttonsTextArray[1] == quiz_userAnswer) ButtonPlaneHandler("Up_Right");
            else if (quiz_buttonsTextArray[2] == quiz_userAnswer) ButtonPlaneHandler("Down_Left");
            else if (quiz_buttonsTextArray[3] == quiz_userAnswer) ButtonPlaneHandler("Down_Right");
        }
        Circle_Plane.SetActive(false); Circle_Text.text = " ";
        if (quiz_userAnswer != null) DisableNextButton();
        else
        {
            Next_Button.enabled = false; Next_Plane.SetActive(false); Next_Text.text = " ";
        }
        if (timeRemaining3 == 100) timerIsRunning3 = true; // To start timer at quiz begin 
        if (timerIsRunning3 == false) timerIsRunning3 = true; // To start timer from being pause 
    }
    public void PageLoader_12() // This function loads the gui elements of page number 12
    {
        pageIndex = 12;
        timerIsRunning2 = false; // Kill timer of next button
        timerIsRunning3 = false; // Kill timer of quiz time
        Up_Title_Text.text = " ";
        Middle_Title_Text.text = "Your answer is:";
        Question_Title_Text.text = " ";
        Time_Title_Text.text = " ";
        Score_Title_Text.text = " ";
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_firstNumber + "_3D_Quiz1").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField(quiz_operatorSign + "_3D_Quiz").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_secondNumber + "_3D_Quiz2").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_firstNumber + "_3D_Result1").GetValue(this); my3Dobject.SetActive(true);
        my3Dobject = (GameObject)this.GetType().GetField(quiz_operatorSign + "_3D_Result").GetValue(this); my3Dobject.SetActive(true);
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_secondNumber + "_3D_Result2").GetValue(this); my3Dobject.SetActive(true);
        quiz_buttonsTextArray[0] = Up_Left_Button_Text.GetParsedText();
        Up_Left_Button.enabled = false; Up_Left_Button_Plane.SetActive(false); Up_Left_Button_Text.text = " ";
        quiz_buttonsTextArray[1] = Up_Right_Button_Text.GetParsedText();
        Up_Right_Button.enabled = false; Up_Right_Button_Plane.SetActive(false); Up_Right_Button_Text.text = " ";
        quiz_buttonsTextArray[2] = Down_Left_Button_Text.GetParsedText();
        Down_Left_Button.enabled = false; Down_Left_Button_Plane.SetActive(false); Down_Left_Button_Text.text = " ";
        quiz_buttonsTextArray[3] = Down_Right_Button_Text.GetParsedText();
        Down_Right_Button.enabled = false; Down_Right_Button_Plane.SetActive(false); Down_Right_Button_Text.text = " ";
        Next_Button.enabled = false; Next_Text.text = " "; Next_Plane.SetActive(false);
        Circle_Plane.SetActive(true); Circle_Text.text = quiz_userAnswer;
        timerIsRunning1 = true; timeRemaining1 = 3; //Start timer, Set time duration
    }
    public void PageLoader_13() // This function loads the gui elements of page number 13
    {
        pageIndex = 13;
        timerIsRunning2 = false; // Kill timer of next button
        timerIsRunning3 = false; // Kill timer of quiz time
        Up_Title_Text.text = "Question result is:";
        Question_Title_Text.text = " ";
        Time_Title_Text.text = " ";
        Score_Title_Text.text = " ";
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_firstNumber + "_3D_Quiz1").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField(quiz_operatorSign + "_3D_Quiz").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_secondNumber + "_3D_Quiz2").GetValue(this); my3Dobject.SetActive(false);
        quiz_buttonsTextArray[0] = Up_Left_Button_Text.GetParsedText();
        Up_Left_Button.enabled = false; Up_Left_Button_Plane.SetActive(false); Up_Left_Button_Text.text = " ";
        quiz_buttonsTextArray[1] = Up_Right_Button_Text.GetParsedText();
        Up_Right_Button.enabled = false; Up_Right_Button_Plane.SetActive(false); Up_Right_Button_Text.text = " ";
        quiz_buttonsTextArray[2] = Down_Left_Button_Text.GetParsedText();
        Down_Left_Button.enabled = false; Down_Left_Button_Plane.SetActive(false); Down_Left_Button_Text.text = " ";
        quiz_buttonsTextArray[3] = Down_Right_Button_Text.GetParsedText();
        Down_Right_Button.enabled = false; Down_Right_Button_Plane.SetActive(false); Down_Right_Button_Text.text = " ";
        Next_Button.enabled = false; Next_Text.text = " "; Next_Plane.SetActive(false);
        Circle_Plane.SetActive(true);
        if (quiz_userAnswer == Convert.ToString(quiz_answer1))
        {
            Checkmark_3D.SetActive(true); Correct_Wrong_Text.text = "Correct";
        }
        else
        {
            Crossmark_3D.SetActive(true); Correct_Wrong_Text.text = "Wrong";
        }
        timerIsRunning1 = true; timeRemaining1 = 3; //Start timer, Set time duration
    }
    public void PageLoader_14() // This function loads the gui elements of page number 14
    {
        pageIndex = 14;
        timerIsRunning3 = false; //Kill timer of quiz time
        Up_Title_Text.text = " ";
        Middle_Title_Text.text = "Finished";
        Down_Title_Text.text = " ";
        Emoji_Text.text = "<sprite name=\"Emojis_7\">";
        Correct_Wrong_Text.text = " ";
        Checkmark_3D.SetActive(false); Crossmark_3D.SetActive(false); Circle_Plane.SetActive(false);
        Next_Button.enabled = false; Next_Plane.SetActive(false); Next_Text.text = " ";
        Question_Title_Text.text = " ";
        Time_Title_Text.text = " ";
        Score_Title_Text.text = " ";
        timerIsRunning1 = true; timeRemaining1 = 3; //Start timer, Set time duration
    }
    public void PageLoader_15() // This function loads the gui elements of page number 15
    {
        pageIndex = 15;
        timerIsRunning3 = false; //Kill timer of quiz time
        Up_Title_Text.text = " ";
        Middle_Title_Text.text = "Timeout";
        Down_Title_Text.text = " ";
        Emoji_Text.text = "<sprite name=\"Emojis_6\">";
        Correct_Wrong_Text.text = " ";
        Words_ObjectName_Text.text = " ";
        Checkmark_3D.SetActive(false); Crossmark_3D.SetActive(false); Circle_Plane.SetActive(false);
        Question_Title_Text.text = " ";
        Time_Title_Text.text = " ";
        Score_Title_Text.text = " ";
        if (selectedSubject == "Math")
        {
            my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_firstNumber + "_3D_Quiz1").GetValue(this); my3Dobject.SetActive(false);
            my3Dobject = (GameObject)this.GetType().GetField(quiz_operatorSign + "_3D_Quiz").GetValue(this); my3Dobject.SetActive(false);
            my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_secondNumber + "_3D_Quiz2").GetValue(this); my3Dobject.SetActive(false);
            my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_firstNumber + "_3D_Result1").GetValue(this); my3Dobject.SetActive(false);
            my3Dobject = (GameObject)this.GetType().GetField(quiz_operatorSign + "_3D_Result").GetValue(this); my3Dobject.SetActive(false);
            my3Dobject = (GameObject)this.GetType().GetField("Number_" + quiz_secondNumber + "_3D_Result2").GetValue(this); my3Dobject.SetActive(false);
        }
        else if (selectedSubject == "Words")
        {
            my3Dobject = (GameObject)this.GetType().GetField(Words_Array[quiz_WordsQuestionsIndexes[quiz_questionIndex], 1]).GetValue(this); my3Dobject.SetActive(false);
        }
        Up_Left_Button.enabled = false; Up_Left_Button_Plane.SetActive(false); Up_Left_Button_Text.text = " ";
        Up_Right_Button.enabled = false; Up_Right_Button_Plane.SetActive(false); Up_Right_Button_Text.text = " ";
        Down_Left_Button.enabled = false; Down_Left_Button_Plane.SetActive(false); Down_Left_Button_Text.text = " ";
        Down_Right_Button.enabled = false; Down_Right_Button_Plane.SetActive(false); Down_Right_Button_Text.text = " ";
        Left_Button.enabled = false; Left_Button_Plane.SetActive(false); Left_Button_Text.text = " ";
        Right_Button.enabled = false; Right_Button_Plane.SetActive(false); Right_Button_Text.text = " ";
        Circle_Plane.SetActive(false); Circle_Text.text = " ";
        timerIsRunning1 = true; timeRemaining1 = 3; //Start timer, Set time duration
    }
    public void PageLoader_16() // This function loads the gui elements of page number 16
    {
        DisableRetryHomeButton(); // To fade in retry, home buttons after few moments
        pageIndex = 16;
        Next_Button.enabled = false; Next_Plane.SetActive(false); Next_Text.text = " ";
        Middle_Title_Text.text = "Results";
        Emoji_Text.text = " ";
        if (quiz_questionIndex == 11) Quiz_Result_Text.text = "Remaining Questions: 0\nTime Elapsed: " + Convert.ToString(100-Convert.ToInt32(timeRemaining3)) + " seconds\nYour Score: " + quiz_score * 10;
        else Quiz_Result_Text.text = "Remaining Questions: "+(10 - quiz_questionIndex)+"\nTime Elapsed: " + Convert.ToString(100-Convert.ToInt32(timeRemaining3)) + " seconds\nYour Score: " + quiz_score * 10;
    }
    public void PageLoader_17() // This function loads the gui elements of page number 17
    {
        DisableNextButton(); // To fade in the next button after few moments
        pageIndex = 17;
        Up_Title_Text.text = " ";
        Middle_Title_Text.text = "Choose Letter";
        Down_Title_Text.text = " ";
        Left_Rectangle_Button.enabled = false; Left_Rectangle_Plane.SetActive(false); Left_Rectangle_Text.text = " ";
        Right_Rectangle_Button.enabled = false; Right_Rectangle_Plane.SetActive(false); Right_Rectangle_Text.text = " ";
        Home_Button.enabled = false; Home_Plane.SetActive(false); Home_Text.text = " ";
        Retry_Button.enabled = false; Retry_Plane.SetActive(false); Retry_Text.text = " ";
        Clock_3D.SetActive(false); Book2_3D.SetActive(false);
        myLetter = Words_Array[myLetterArrayIndex, 0]; // Make letter A visable by default
        my3Dobject = (GameObject)this.GetType().GetField("Letter_" + myLetter + "_3D").GetValue(this); my3Dobject.SetActive(true);
        Up_Left_Button.enabled = true; Up_Left_Button_Plane.SetActive(true); Up_Left_Button_Text.text = "<";
        Up_Right_Button.enabled = true; Up_Right_Button_Plane.SetActive(true); Up_Right_Button_Text.text = ">";
        Home_Button.enabled = false; Home_Plane.SetActive(false); Home_Text.text = " ";
        Retry_Button.enabled = false; Retry_Plane.SetActive(false); Retry_Text.text = " ";
        Circle_Plane.SetActive(false);
        Up_Left_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_90dgree_Texture;
        Up_Right_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_270dgree_Texture;
    }
    public void PageLoader_18() // This function loads the gui elements of page number 18
    {
        DisableRetryHomeButton(); // To fade in retry, home buttons after few moments
        pageIndex = 18;
        Up_Title_Text.text = "Word start with " + Words_Array[myLetterArrayIndex, 0] + " is:";
        Middle_Title_Text.text = " ";
        Up_Left_Button.enabled = false; Up_Left_Button_Plane.SetActive(false); Up_Left_Button_Text.text = " ";
        Up_Right_Button.enabled = false; Up_Right_Button_Plane.SetActive(false); Up_Right_Button_Text.text = " ";
        Next_Button.enabled = false; Next_Plane.SetActive(false); Next_Text.text = " ";
        Circle_Plane.SetActive(true);
        my3Dobject = (GameObject)this.GetType().GetField("Letter_" + myLetter + "_3D").GetValue(this); my3Dobject.SetActive(false);
        my3Dobject = (GameObject)this.GetType().GetField("" + Words_Array[myLetterArrayIndex, 1]).GetValue(this); my3Dobject.SetActive(true);
        Words_ObjectName_Text.text = Words_Array[myLetterArrayIndex, 2];
    }
    public void PageLoader_19() // This function loads the gui elements of page number 19
    {
        pageIndex = 19;
        Up_Title_Text.text = "Question       Time          Score";
        Middle_Title_Text.text = " ";
        Down_Title_Text.text = " ";
        Emoji_Text.text = " ";
        Words_ObjectName_Text.text = " ";
        Checkmark_3D.SetActive(false); Crossmark_3D.SetActive(false);
        Correct_Wrong_Text.text = " ";
        if (quiz_questionIndex != 0) // Not in first question
        {
            if (quiz_userAnswer == null) // No answer means new question
            {
                my3Dobject = (GameObject)this.GetType().GetField(Words_Array[quiz_WordsQuestionsIndexes[quiz_questionIndex], 1]).GetValue(this); my3Dobject.SetActive(false);
                Left_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_90dgree_Texture;
                Right_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_270dgree_Texture;
            }
        }
        if (quiz_questionIndex == 0)
        {
            GenerateWordsQuestions(); // Create random questions array
            quiz_questionIndex++; // Start first question
            Left_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_90dgree_Texture;
            Right_Button_Plane.GetComponent<Renderer>().material.mainTexture = Normal_270dgree_Texture;
        }
        QuestionOrderHandler();
        quiz_nextQuestion = false;
        my3Dobject = (GameObject)this.GetType().GetField(Words_Array[quiz_WordsQuestionsIndexes[quiz_questionIndex], 1]).GetValue(this); my3Dobject.SetActive(true);
        Left_Button.enabled = true; Left_Button_Plane.SetActive(true); Left_Button_Text.text = quiz_wordsAnswer1;
        Right_Button.enabled = true; Right_Button_Plane.SetActive(true); Right_Button_Text.text = quiz_wordsAnswer2;
        Circle_Plane.SetActive(false); Circle_Text.text = " ";
        if (quiz_userAnswer != null) DisableNextButton();
        else
        {
            Next_Button.enabled = false; Next_Plane.SetActive(false); Next_Text.text = " ";
        }
        if (timeRemaining3 == 100) timerIsRunning3 = true; // To start timer at quiz begin 
        if (timerIsRunning3 == false) timerIsRunning3 = true; // To start timer from being pause 
    }
    public void PageLoader_20() // This function loads the gui elements of page number 20
    {
        pageIndex = 20;
        timerIsRunning2 = false; // Kill timer of next button
        timerIsRunning3 = false; // Kill timer of quiz time
        Up_Title_Text.text = "Your answer is:";
        Question_Title_Text.text = " ";
        Time_Title_Text.text = " ";
        Score_Title_Text.text = " ";
        Left_Button.enabled = false; Left_Button_Plane.SetActive(false); Left_Button_Text.text = " ";
        Right_Button.enabled = false; Right_Button_Plane.SetActive(false); Right_Button_Text.text = " ";
        Next_Button.enabled = false; Next_Plane.SetActive(false); Next_Text.text = " ";
        Circle_Plane.SetActive(true);
        Words_ObjectName_Text.text = quiz_userAnswer;
        timerIsRunning1 = true; timeRemaining1 = 3; //Start timer, Set time duration
    }
    public void PageLoader_21() // This function loads the gui elements of page number 21
    {
        pageIndex = 21;
        timerIsRunning2 = false; // Kill timer of next button
        timerIsRunning3 = false; // Kill timer of quiz time
        Up_Title_Text.text = "Question result is:";
        Question_Title_Text.text = " ";
        Time_Title_Text.text = " ";
        Score_Title_Text.text = " ";
        my3Dobject = (GameObject)this.GetType().GetField(Words_Array[quiz_WordsQuestionsIndexes[quiz_questionIndex], 1]).GetValue(this); my3Dobject.SetActive(false);
        Left_Button.enabled = false; Left_Button_Plane.SetActive(false); Left_Button_Text.text = " ";
        Right_Button.enabled = false; Right_Button_Plane.SetActive(false); Right_Button_Text.text = " ";
        Next_Button.enabled = false; Next_Plane.SetActive(false); Next_Text.text = " ";
        Circle_Plane.SetActive(true);
        if (quiz_userAnswer == Words_Array[quiz_WordsQuestionsIndexes[quiz_questionIndex], 2])
        {
            Checkmark_3D.SetActive(true); Correct_Wrong_Text.text = "Correct";
        }
        else
        {
            Crossmark_3D.SetActive(true); Correct_Wrong_Text.text = "Wrong";
        }
        timerIsRunning1 = true; timeRemaining1 = 3; //Start timer, Set time duration
    }
    void Start() // Everything written inside this function will execute once when progarm being started
    {
        // Register buttons with their event listeners
        Next_Button.RegisterOnButtonPressed(NextButtonListener);
        Left_Rectangle_Button.RegisterOnButtonPressed(LeftRectangleButtonListener);
        Right_Rectangle_Button.RegisterOnButtonPressed(RightRectangleButtonListener);
        Left_Button.RegisterOnButtonPressed(LeftButtonListener);
        Right_Button.RegisterOnButtonPressed(RightButtonListener);
        Up_Left_Button.RegisterOnButtonPressed(UpLeftButtonListener);
        Up_Right_Button.RegisterOnButtonPressed(UpRightButtonListener);
        Down_Left_Button.RegisterOnButtonPressed(DownLeftButtonListener);
        Down_Right_Button.RegisterOnButtonPressed(DownRightButtonListener);
        Home_Button.RegisterOnButtonPressed(HomeButtonListener);
        Retry_Button.RegisterOnButtonPressed(RetryButtonListener);
        // Making all pages elements disabled by default
        Info_Plane.SetActive(false); Cube123_3D.SetActive(false); CubeABC_3D.SetActive(false);
        Cube123_3D_Focused.SetActive(false); CubeABC_3D_Focused.SetActive(false); Clock_3D.SetActive(false);
        Book2_3D.SetActive(false); Clock_3D_Focused.SetActive(false); Book2_3D_Focused.SetActive(false);
        Number_0_3D_Learn.SetActive(false); Number_1_3D_Learn.SetActive(false); Number_2_3D_Learn.SetActive(false);
        Number_3_3D_Learn.SetActive(false); Number_4_3D_Learn.SetActive(false); Number_5_3D_Learn.SetActive(false);
        Number_6_3D_Learn.SetActive(false); Number_7_3D_Learn.SetActive(false); Number_8_3D_Learn.SetActive(false);
        Number_9_3D_Learn.SetActive(false); Number_0_3D_Result1.SetActive(false); Number_1_3D_Result1.SetActive(false);
        Number_2_3D_Result1.SetActive(false); Number_3_3D_Result1.SetActive(false); Number_4_3D_Result1.SetActive(false);
        Number_5_3D_Result1.SetActive(false); Number_6_3D_Result1.SetActive(false); Number_7_3D_Result1.SetActive(false);
        Number_8_3D_Result1.SetActive(false); Number_9_3D_Result1.SetActive(false); Number_0_3D_Result2.SetActive(false);
        Number_1_3D_Result2.SetActive(false); Number_2_3D_Result2.SetActive(false); Number_3_3D_Result2.SetActive(false);
        Number_4_3D_Result2.SetActive(false); Number_5_3D_Result2.SetActive(false); Number_6_3D_Result2.SetActive(false);
        Number_7_3D_Result2.SetActive(false); Number_8_3D_Result2.SetActive(false); Number_9_3D_Result2.SetActive(false);
        Number_0_3D_Quiz1.SetActive(false); Number_1_3D_Quiz1.SetActive(false); Number_2_3D_Quiz1.SetActive(false);
        Number_3_3D_Quiz1.SetActive(false); Number_4_3D_Quiz1.SetActive(false); Number_5_3D_Quiz1.SetActive(false);
        Number_6_3D_Quiz1.SetActive(false); Number_7_3D_Quiz1.SetActive(false); Number_8_3D_Quiz1.SetActive(false);
        Number_9_3D_Quiz1.SetActive(false); Number_0_3D_Quiz2.SetActive(false); Number_1_3D_Quiz2.SetActive(false);
        Number_2_3D_Quiz2.SetActive(false); Number_3_3D_Quiz2.SetActive(false); Number_4_3D_Quiz2.SetActive(false);
        Number_5_3D_Quiz2.SetActive(false); Number_6_3D_Quiz2.SetActive(false); Number_7_3D_Quiz2.SetActive(false);
        Number_8_3D_Quiz2.SetActive(false); Number_9_3D_Quiz2.SetActive(false); Addition_3D.SetActive(false);
        Addition_3D_Result.SetActive(false); Addition_3D_Quiz.SetActive(false); Substraction_3D.SetActive(false);
        Substraction_3D_Result.SetActive(false); Substraction_3D_Quiz.SetActive(false);
        Division_3D.SetActive(false); Division_3D_Result.SetActive(false); Division_3D_Quiz.SetActive(false);
        Multiplication_3D.SetActive(false); Multiplication_3D_Result.SetActive(false); Multiplication_3D_Quiz.SetActive(false);
        Checkmark_3D.SetActive(false); Crossmark_3D.SetActive(false); Letter_A_3D.SetActive(false);
        Letter_B_3D.SetActive(false); Letter_C_3D.SetActive(false); Letter_D_3D.SetActive(false);
        Letter_E_3D.SetActive(false); Letter_F_3D.SetActive(false); Letter_G_3D.SetActive(false);
        Letter_H_3D.SetActive(false); Letter_I_3D.SetActive(false); Letter_J_3D.SetActive(false);
        Letter_K_3D.SetActive(false); Letter_L_3D.SetActive(false); Letter_M_3D.SetActive(false);
        Letter_N_3D.SetActive(false); Letter_O_3D.SetActive(false); Letter_P_3D.SetActive(false);
        Letter_Q_3D.SetActive(false); Letter_R_3D.SetActive(false); Letter_S_3D.SetActive(false);
        Letter_T_3D.SetActive(false); Letter_U_3D.SetActive(false); Letter_V_3D.SetActive(false);
        Letter_W_3D.SetActive(false); Letter_X_3D.SetActive(false); Letter_Y_3D.SetActive(false);
        Letter_Z_3D.SetActive(false); Apple_3D.SetActive(false); Ball_3D.SetActive(false);
        Cat_3D.SetActive(false); Dog_3D.SetActive(false); Earth_3D.SetActive(false);
        Flag_3D.SetActive(false); Grass_3D.SetActive(false); Headphones_3D.SetActive(false);
        IceCream_3D.SetActive(false); Jewel_3D.SetActive(false); Key_3D.SetActive(false);
        Lion_3D.SetActive(false); Mail_3D.SetActive(false); Note_3D.SetActive(false);
        Orange_3D.SetActive(false); Plane_3D.SetActive(false); Queen_3D.SetActive(false);
        Rose_3D.SetActive(false); Strawberry_3D.SetActive(false); Turtle_3D.SetActive(false);
        Umbrella_3D.SetActive(false); Virus_3D.SetActive(false); Watermelon_3D.SetActive(false);
        Xylophone_3D.SetActive(false); Yacht_3D.SetActive(false); Zebra_3D.SetActive(false);
        PageLoader_1(); // Start at page 1
    }
    void Update() // Everything written inside this function will execute every second
    {
        GamePathTextChanger(); // To update game path text every second
        if (timerIsRunning1) // Everything written inside this function will execute when timer bool is true
        {
            if (timeRemaining1 > 0) timeRemaining1 -= Time.deltaTime; // Decrease 1 second of time remaining evrey second
            else // When timer is 0 (finished) do the following
            {
                timeRemaining1 = 0; timerIsRunning1 = false; // Turning off the timer by change bool to false, time remaining to 0
                if (pageIndex == 3) PageLoader_2();
                else if (pageIndex == 5) PageLoader_4();
                else if (pageIndex == 12) PageLoader_11();
                else if (pageIndex == 13)
                {
                    if (quiz_questionIndex == 11) PageLoader_14();
                    else PageLoader_11();
                }
                else if (pageIndex == 14 || pageIndex == 15) PageLoader_16();
                else if (pageIndex == 20) PageLoader_19();
                else if (pageIndex == 21)
                {
                    if (quiz_questionIndex == 10) PageLoader_14();
                    else
                    {
                        quiz_questionIndex++; PageLoader_19();
                    }
                }
            }
        }
        if (timerIsRunning2) // Everything written inside this function will execute when timer bool is true
        {
            if (timeRemaining2 > 0) timeRemaining2 -= Time.deltaTime; // Decrease 1 second of time remaining evrey second
            else // When timer is 0 (finished) do the following
            {
                timeRemaining2 = 0; timerIsRunning2 = false; // Turning off the timer by change bool to false, time remaining to 0
                if (myRetryHomeBool) EnableRetryHomeButton();
                else EnableNextButton();
            }
        }
        if (timerIsRunning3) // Everything written inside this function will execute when timer bool is true
        {
            if (timeRemaining3 > 0)
            {
                if (pageIndex == 11 || pageIndex == 12 || pageIndex == 19) // Render quiz question, time and score text
                {
                    Question_Title_Text.text = quiz_questionIndex + "/10";
                    Time_Title_Text.text = Convert.ToString(Convert.ToInt32(timeRemaining3));
                    Score_Title_Text.text = "" + quiz_score * 10;
                }
                timeRemaining3 -= Time.deltaTime; // Decrease 1 second of time remaining evrey second
            }
            else
            {
                timeRemaining3 = 0; timerIsRunning3 = false; // Turning off the timer by change bool to false, time remaining to 0
                PageLoader_15(); // Timeout Page
            }
        }
    }
}
