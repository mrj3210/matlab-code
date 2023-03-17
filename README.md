# matlab-code
classdef CoreAppNew < matlab.apps.AppBase

    % Properties that correspond to app components
    properties (Access = public)
        UIFigure                  matlab.ui.Figure
        SelectPlayerButtonGroup   matlab.ui.container.ButtonGroup
        Player2Button             matlab.ui.control.RadioButton
        Player1Button             matlab.ui.control.RadioButton
        Lamp16                    matlab.ui.control.Lamp
        Lamp15                    matlab.ui.control.Lamp
        Lamp14                    matlab.ui.control.Lamp
        Lamp13                    matlab.ui.control.Lamp
        Lamp12                    matlab.ui.control.Lamp
        Lamp11                    matlab.ui.control.Lamp
        Lamp10                    matlab.ui.control.Lamp
        Lamp9                     matlab.ui.control.Lamp
        Lamp8                     matlab.ui.control.Lamp
        Lamp7                     matlab.ui.control.Lamp
        Lamp6                     matlab.ui.control.Lamp
        Lamp5                     matlab.ui.control.Lamp
        Lamp4                     matlab.ui.control.Lamp
        Lamp3                     matlab.ui.control.Lamp
        Lamp2                     matlab.ui.control.Lamp
        Lamp1                     matlab.ui.control.Lamp
        WINNEREditField           matlab.ui.control.EditField
        WINNEREditFieldLabel      matlab.ui.control.Label
        Image4                    matlab.ui.control.Image
        Image3                    matlab.ui.control.Image
        HoldDice1CheckBox         matlab.ui.control.CheckBox
        HoldDice2CheckBox         matlab.ui.control.CheckBox
        HoldDice6CheckBox         matlab.ui.control.CheckBox
        HoldDice5CheckBox         matlab.ui.control.CheckBox
        HoldDice4CheckBox         matlab.ui.control.CheckBox
        HoldDice3CheckBox         matlab.ui.control.CheckBox
        Dice6EditField            matlab.ui.control.NumericEditField
        Dice6Label                matlab.ui.control.Label
        Dice5EditField            matlab.ui.control.NumericEditField
        Dice5Label                matlab.ui.control.Label
        Dice4EditField            matlab.ui.control.NumericEditField
        Dice4Label                matlab.ui.control.Label
        Dice1EditField            matlab.ui.control.NumericEditField
        Dice1Label                matlab.ui.control.Label
        Dice2EditField            matlab.ui.control.NumericEditField
        Dice2Label                matlab.ui.control.Label
        Dice3EditField            matlab.ui.control.NumericEditField
        Dice3Label                matlab.ui.control.Label
        TotalValueEditField       matlab.ui.control.NumericEditField
        TotalValueEditFieldLabel  matlab.ui.control.Label
        Player2EditField          matlab.ui.control.NumericEditField
        Player2EditFieldLabel     matlab.ui.control.Label
        Player1EditField          matlab.ui.control.NumericEditField
        Player1EditFieldLabel     matlab.ui.control.Label
        Image                     matlab.ui.control.Image
        ZonkLabel                 matlab.ui.control.Label
        EndTurnButton             matlab.ui.control.Button
        RollButton                matlab.ui.control.Button
    end

    
    properties (Access = public)

        % Thingspeak
  
  channelID = 2068752;
    
  writeKey = 'Y4AKTS0J859VQKCM';
    
  readKey = '8Y1MICFEICT9ECWT';

  readDelay = 3;

  writeDelay = 3;

    end

   methods (Access = public)

% Dice Values added if boxes checked

        function results = total(app)
                        tempArray = [];

           if app.HoldDice1CheckBox.Value == true
                tempArray = [tempArray, app.Dice1EditField.Value];
           end

           if app.HoldDice2CheckBox.Value == true
                tempArray = [tempArray, app.Dice2EditField.Value];
           end

           if app.HoldDice3CheckBox.Value == true
                 tempArray = [tempArray, app.Dice3EditField.Value];
           end

           if app.HoldDice4CheckBox.Value == true
                 tempArray = [tempArray, app.Dice4EditField.Value];
           end

           if app.HoldDice5CheckBox.Value == true
                  tempArray = [tempArray, app.Dice5EditField.Value];
           end

           if app.HoldDice6CheckBox.Value == true
                  tempArray = [tempArray, app.Dice6EditField.Value];
           end

% Point Values

 tempPoints = 0;

 % for 3 pairs

if sum(tempArray(:) == 1) == 2 && sum(tempArray(:) == 2) == 2 ... 
        && sum(tempArray(:) == 3) == 2

    tempPoints = 800 + tempPoints;
end

if sum(tempArray(:) == 1) == 2 && sum(tempArray(:) == 2) == 2 ... 
        && sum(tempArray(:) == 4) == 2

    tempPoints = 800 + tempPoints;
end

if sum(tempArray(:) == 1) == 2 && sum(tempArray(:) == 2) == 2 ... 
        && sum(tempArray(:) == 5) == 2

    tempPoints = 700 + tempPoints;
end

if sum(tempArray(:) == 1) == 2 && sum(tempArray(:) == 2) == 2 ... 
        && sum(tempArray(:) == 6) == 2

    tempPoints = 800 + tempPoints;
end

if sum(tempArray(:) == 1) == 2 && sum(tempArray(:) == 3) == 2 ... 
        && sum(tempArray(:) == 4) == 2

    tempPoints = 800 + tempPoints;
end

if sum(tempArray(:) == 1) == 2 && sum(tempArray(:) == 3) == 2 ... 
        && sum(tempArray(:) == 5) == 2

    tempPoints = 700 + tempPoints;
end

if sum(tempArray(:) == 1) == 2 && sum(tempArray(:) == 3) == 2 ... 
        && sum(tempArray(:) == 6) == 2

    tempPoints = 800 + tempPoints;
end

if sum(tempArray(:) == 1) == 2 && sum(tempArray(:) == 4) == 2 ... 
        && sum(tempArray(:) == 5) == 2

    tempPoints = 700 + tempPoints;
end

if sum(tempArray(:) == 1) == 2 && sum(tempArray(:) == 4) == 2 ... 
        && sum(tempArray(:) == 6) == 2

    tempPoints = 800 + tempPoints;
end

if sum(tempArray(:) == 1) == 2 && sum(tempArray(:) == 5) == 2 ... 
        && sum(tempArray(:) == 6) == 2

    tempPoints = 700 + tempPoints;
end

if sum(tempArray(:) == 2) == 2 && sum(tempArray(:) == 3) == 2 ... 
        && sum(tempArray(:) == 4) == 2

    tempPoints = 1000 + tempPoints;
end

if sum(tempArray(:) == 2) == 2 && sum(tempArray(:) == 3) == 2 ... 
        && sum(tempArray(:) == 5) == 2

    tempPoints = 900 + tempPoints;
end

if sum(tempArray(:) == 2) == 2 && sum(tempArray(:) == 3) == 2 ... 
        && sum(tempArray(:) == 6) == 2

    tempPoints = 1000 + tempPoints;
end

if sum(tempArray(:) == 2) == 2 && sum(tempArray(:) == 4) == 2 ... 
        && sum(tempArray(:) == 5) == 2

    tempPoints = 900 + tempPoints;
end

if sum(tempArray(:) == 2) == 2 && sum(tempArray(:) == 4) == 2 ... 
        && sum(tempArray(:) == 6) == 2

    tempPoints = 1000 + tempPoints;
end

if sum(tempArray(:) == 2) == 2 && sum(tempArray(:) == 5) == 2 ... 
        && sum(tempArray(:) == 6) == 2

    tempPoints = 900 + tempPoints;
end

if sum(tempArray(:) == 3) == 2 && sum(tempArray(:) == 4) == 2 ... 
        && sum(tempArray(:) == 5) == 2

    tempPoints = 900 + tempPoints;
end

if sum(tempArray(:) == 3) == 2 && sum(tempArray(:) == 4) == 2 ... 
        && sum(tempArray(:) == 6) == 2

    tempPoints = 1000 + tempPoints;
end

if sum(tempArray(:) == 3) == 2 && sum(tempArray(:) == 5) == 2 ... 
        && sum(tempArray(:) == 6) == 2

    tempPoints = 900 + tempPoints;
end

if sum(tempArray(:) == 4) == 2 && sum(tempArray(:) == 5) == 2 ... 
        && sum(tempArray(:) == 6) == 2

    tempPoints = 900 + tempPoints;
end

 % for 5s
           if sum(tempArray(:) == 5) == 1

               tempPoints = 50 + tempPoints;
           end
            
           if sum(tempArray(:) == 5) == 2

               tempPoints = 100 + tempPoints;
           end
            
           if sum(tempArray(:) == 5) == 3

               tempPoints = 500 + tempPoints;
           end

           if sum(tempArray(:) == 5) == 4

               tempPoints = 1000 + tempPoints;
           end

           if sum(tempArray(:) == 5) == 5

               tempPoints = 2000 + tempPoints;
           end
           
           if sum(tempArray(:) == 5) == 6
               tempPoints = 4000 + tempPoints;
           end

% for 1s
     
           if sum(tempArray(:) == 1) == 1
               tempPoints = 100 + tempPoints;
           end

           if sum(tempArray(:) == 1) == 2
               tempPoints = 200 + tempPoints;
           end
           
           if sum(tempArray(:) == 1) == 3
               tempPoints = 1000 + tempPoints;
           end
           
           if sum(tempArray(:) == 1) == 4
               tempPoints = 2000 + tempPoints;
           end

           if sum(tempArray(:) == 1) == 5
               tempPoints = 4000 + tempPoints;
           end

           if sum(tempArray(:) == 1) == 6
               tempPoints = 5000 + tempPoints;
           end

% for 2s

           if sum(tempArray(:) == 2) == 3
               tempPoints = 200 + tempPoints;
           end

           if sum(tempArray(:) == 2) == 4
               tempPoints = 400 + tempPoints;
           end
           
           if sum(tempArray(:) == 2) == 5
               tempPoints = 800 + tempPoints;
           end
           
           if sum(tempArray(:) == 2) == 6
               tempPoints = 1600 + tempPoints;
           end   
          
% for 3s
           if sum(tempArray(:) == 3) == 3
               tempPoints = 300 + tempPoints;
           end

           if sum(tempArray(:) == 3) == 4
               tempPoints = 600 + tempPoints;
           end
           
           if sum(tempArray(:) == 3) == 5
               tempPoints = 1200 + tempPoints;
           end
           
           if sum(tempArray(:) == 3) == 6
               tempPoints = 2400 + tempPoints;
           end 
            
% for 4s

           if sum(tempArray(:) == 4) == 3
               tempPoints = 400 + tempPoints;
           end

           if sum(tempArray(:) == 4) == 4
               tempPoints = 800 + tempPoints;
           end
           
           if sum(tempArray(:) == 4) == 5
               tempPoints = 1600 + tempPoints;
           end
           
           if sum(tempArray(:) == 4) == 6
               tempPoints = 3200 + tempPoints;
           end 

% for 6s
           if sum(tempArray(:) == 6) == 3
               tempPoints = 600 + tempPoints;
           end

           if sum(tempArray(:) == 6) == 4
               tempPoints = 1200 + tempPoints;
           end
           
           if sum(tempArray(:) == 6) == 5
               tempPoints = 2400 + tempPoints;
           end
           
           if sum(tempArray(:) == 6) == 6
               tempPoints = 4800 + tempPoints;
           end 

% for straight

           if sum(tempArray(:) == 1) == 1 && ...
              sum(tempArray(:) == 2) == 1 && ...
              sum(tempArray(:) == 3) == 1 && ...
              sum(tempArray(:) == 4) == 1 && ...
              sum(tempArray(:) == 5) == 1 && ...
              sum(tempArray(:) == 6) == 1
               
                tempPoints = 1350 + tempPoints;
           end


% for when no points are possible (farkle)(unfinished)


             results = tempPoints;

% when game won (unfinished)

             if app.Player1EditField.Value > 5000
                app.WINNEREditField.Value = disp('Player 1 !!!');
                % win sound effect plays
             end

             if app.Player2EditField.Value > 5000
                 app.WINNEREditField.Value = disp('Player 2 !!!');
                 % win sound effect plays
             end
        end
    end
    

    % Callbacks that handle component events
    methods (Access = private)

        % Code that executes after component creation
        function startupFcn(app)
            
            
           % Thingspeak

thingSpeakWrite(app.channelID, 'Fields', 1, 'writeKey', app.writeKey,...
    'Values',app.Player1EditField.Value);

pause(2);

thingSpeakWrite(app.channelID, 'Fields', 2, 'writeKey', app.writeKey,...
    'Values', app.Player2EditField.Value);

pause(2);

app.Player1EditField.Value = thingSpeakRead(app.channelID, 'Fields', 1,...
    'readKey', app.readKey);

pause(2);

app.Player2EditField.Value = thingSpeakRead(app.channelID, 'Fields', 2,...
    'readKey', app.readKey);

app.Player1EditField.Enable = "off";
app.Player2EditField.Enable = "off";

if app.Player1Button.Value == true
    app.Player1EditField.Enable = "on";
end

if app.Player2Button.Value == true
    app.Player2EditField.Enable = "on";
end


        end

        % Button pushed function: RollButton
        function RollButtonPushed(app, event)

% When roll is pushed, all 6 die are randomly assigned a number
% between 1 to 6 if they are not checked.
            
% Total Value added to total turn of player's sum.

% Next roll, new set of checked boxes values checked and stored.

           [y, Fs] = audioread("DiceRoll.wav");
         
            sound(y,Fs);


% random number 1-6 assigned to non checked dice fields
            
tempArray = [];

 
           if app.HoldDice1CheckBox.Value == false

               app.Dice1EditField.Value = randi(6,1);
           
               else
           tempArray = [tempArray, app.Dice1EditField.Value];
           end

           if app.HoldDice2CheckBox.Value == false

               app.Dice2EditField.Value = randi(6,1);
            
                else
           tempArray = [tempArray, app.Dice2EditField.Value];
           end

           if app.HoldDice3CheckBox.Value == false

               app.Dice3EditField.Value = randi(6,1);
   
                else
           tempArray = [tempArray, app.Dice3EditField.Value];
           end

           if app.HoldDice4CheckBox.Value == false

               app.Dice4EditField.Value = randi(6,1);
       
                else
           tempArray = [tempArray, app.Dice4EditField.Value];
           end

           if app.HoldDice5CheckBox.Value == false

               app.Dice5EditField.Value = randi(6,1);
         
                else
           tempArray = [tempArray, app.Dice5EditField.Value];
           end

            if app.HoldDice6CheckBox.Value == false

               app.Dice6EditField.Value = randi(6,1);

                else
            tempArray = [tempArray, app.Dice6EditField.Value];
            end

        end

        % Value changed function: HoldDice1CheckBox
        function HoldDice1CheckBoxValueChanged(app, event)
            
            % Dice 1 value held if box ticked

            if app.HoldDice1CheckBox.Value == true
                app.Dice1EditField.Enable = "off";
                app.HoldDice1CheckBox.Enable = "off";
            else
                app.Dice1EditField.Enable = "on";
            end

           app.TotalValueEditField.Value = total(app);
        end

        % Value changed function: HoldDice2CheckBox
        function HoldDice2CheckBoxValueChanged(app, event)
            
            % Dice 2 value held if box ticked
             
            if app.HoldDice2CheckBox.Value == true
                app.Dice2EditField.Enable = "off";
                app.HoldDice2CheckBox.Enable = "off";
            else
                app.Dice2EditField.Enable = "on";
            end

            app.TotalValueEditField.Value = total(app);
        end

        % Value changed function: HoldDice3CheckBox
        function HoldDice3CheckBoxValueChanged(app, event)
            
            % Dice 3 value held if box ticked
            
            if app.HoldDice3CheckBox.Value == true
                app.Dice3EditField.Enable = "off";
                app.HoldDice3CheckBox.Enable = "off";
            else
                app.Dice3EditField.Enable = "on";
            end

            app.TotalValueEditField.Value = total(app);
        end

        % Value changed function: HoldDice4CheckBox
        function HoldDice4CheckBoxValueChanged(app, event)
            
            % Dice 4 value held if box ticked

            if app.HoldDice4CheckBox.Value == true
                app.Dice4EditField.Enable = "off";
                app.HoldDice4CheckBox.Enable = "off";
            else
                app.Dice4EditField.Enable = "on";
            end

            app.TotalValueEditField.Value = total(app);
        end

        % Value changed function: HoldDice5CheckBox
        function HoldDice5CheckBoxValueChanged(app, event)
            
            % Dice 5 value held if box ticked
            
            if app.HoldDice5CheckBox.Value == true
                app.Dice5EditField.Enable = "off";
                app.HoldDice5CheckBox.Enable = "off";
            else
                app.Dice5EditField.Enable= "on";
            end

            app.TotalValueEditField.Value = total(app);
        end

        % Value changed function: HoldDice6CheckBox
        function HoldDice6CheckBoxValueChanged(app, event)
          
            % Dice 6 value held if box ticked
            
            if app.HoldDice6CheckBox.Value == true
                app.Dice6EditField.Enable = "off";
                app.HoldDice6CheckBox.Enable = "off";
            else
                app.Dice6EditField.Enable= "on";
            end

            app.TotalValueEditField.Value = total(app);
        end

        % Value changed function: Player1EditField
        function Player1EditFieldValueChanged(app, event)

    
        end

        % Button pushed function: EndTurnButton
        function EndTurnButtonPushed(app, event)




% sound effect for when no points are scored

         if app.TotalValueEditField.Value == 0
             
             [y, Fs] = audioread("WrongSFX.mp3");

             sound(y,Fs);
         end


app.HoldDice1CheckBox.Enable = "on";
app.HoldDice2CheckBox.Enable = "on";
app.HoldDice3CheckBox.Enable = "on";
app.HoldDice4CheckBox.Enable = "on";
app.HoldDice5CheckBox.Enable = "on";
app.HoldDice6CheckBox.Enable = "on";

app.HoldDice1CheckBox.Value = false;
app.HoldDice2CheckBox.Value = false;
app.HoldDice3CheckBox.Value = false;
app.HoldDice4CheckBox.Value = false;
app.HoldDice5CheckBox.Value = false;
app.HoldDice6CheckBox.Value = false;

app.Dice1EditField.Enable = "on";
app.Dice2EditField.Enable = "on";
app.Dice3EditField.Enable = "on";
app.Dice4EditField.Enable = "on";
app.Dice5EditField.Enable = "on";
app.Dice6EditField.Enable = "on";

app.Dice1EditField.Value = 0;
app.Dice2EditField.Value = 0;
app.Dice3EditField.Value = 0;
app.Dice4EditField.Value = 0;
app.Dice5EditField.Value = 0;
app.Dice6EditField.Value = 0;


     if app.HoldDice1CheckBox.Value == true
        app.HoldDice1CheckBox.Value = false;
        app.Dice1EditField.Enable= "on";
     end

     if app.HoldDice2CheckBox.Value == true
        app.HoldDice2CheckBox.Value = false;
        app.Dice2EditField.Enable= "on";
     end

     if app.HoldDice3CheckBox.Value == true
        app.HoldDice3CheckBox.Value = false;
        app.Dice3EditField.Enable= "on";
     end

     if app.HoldDice4CheckBox.Value == true
        app.HoldDice4CheckBox.Value = false;
        app.Dice4EditField.Enable= "on";
     end

     if app.HoldDice5CheckBox.Value == true
        app.HoldDice5CheckBox.Value = false;
        app.Dice5EditField.Enable= "on";
     end

     if app.HoldDice6CheckBox.Value == true
        app.HoldDice6CheckBox.Value = false;
        app.Dice6EditField.Enable= "on";
     end


     if app.Player1Button.Value == true
                app.Player1EditField.Value = app.Player1EditField.Value...
                    + app.TotalValueEditField.Value;
                app.Player1EditField.Enable = "on";

     elseif app.Player2Button.Value == true
                app.Player2EditField.Value = app.Player2EditField.Value...
                    + app.TotalValueEditField.Value;
                app.Player2EditField.Enable = "on";
     end


            app.TotalValueEditField.Value = 0;

         if app.Player1EditField.Value >= 5000
             app.WINNEREditField.Value = "Player 1 !!!";
             app.Lamp1.Visible = "on";
             app.Lamp2.Visible = "on";
             app.Lamp3.Visible = "on";
             app.Lamp4.Visible = "on";
             app.Lamp5.Visible = "on";
             app.Lamp6.Visible = "on";
             app.Lamp7.Visible = "on";
             app.Lamp8.Visible = "on";
             app.Lamp9.Visible = "on";
             app.Lamp10.Visible = "on";
             app.Lamp11.Visible = "on";
             app.Lamp12.Visible = "on";
             app.Lamp13.Visible = "on";
             app.Lamp14.Visible = "on";
             app.Lamp15.Visible = "on";
             app.Lamp16.Visible = "on";


            [y, Fs] = audioread("WinSFX.mp3");
         
            sound(y,Fs);

         end

         if app.Player2EditField.Value >= 5000
             app.WINNEREditField.Value = "Player 2 !!!";
             app.Lamp1.Visible = "on";
             app.Lamp2.Visible = "on";
             app.Lamp3.Visible = "on";
             app.Lamp4.Visible = "on";
             app.Lamp5.Visible = "on";
             app.Lamp6.Visible = "on";
             app.Lamp7.Visible = "on";
             app.Lamp8.Visible = "on";
             app.Lamp9.Visible = "on";
             app.Lamp10.Visible = "on";
             app.Lamp11.Visible = "on";
             app.Lamp12.Visible = "on";
             app.Lamp13.Visible = "on";
             app.Lamp14.Visible = "on";
             app.Lamp15.Visible = "on";
             app.Lamp16.Visible = "on";

            [y, Fs] = audioread("WinSFX.mp3");
         
            sound(y,Fs);

         end

                     % Thingspeak

thingSpeakWrite(app.channelID, 'Fields', 1, 'writeKey', app.writeKey,...
    'Values',app.Player1EditField.Value);

pause(2);

thingSpeakWrite(app.channelID, 'Fields', 2, 'writeKey', app.writeKey,...
    'Values', app.Player2EditField.Value);

pause(2);

app.Player1EditField.Value = thingSpeakRead(app.channelID, 'Fields', 1,...
    'readKey', app.readKey);

pause(2);

app.Player2EditField.Value = thingSpeakRead(app.channelID, 'Fields', 2,...
    'readKey', app.readKey);

        end
    end

    % Component initialization
    methods (Access = private)

        % Create UIFigure and components
        function createComponents(app)

            % Get the file path for locating images
            pathToMLAPP = fileparts(mfilename('fullpath'));

            % Create UIFigure and hide until all components are created
            app.UIFigure = uifigure('Visible', 'off');
            app.UIFigure.Color = [0.5686 0.1294 0.1294];
            app.UIFigure.Position = [100 100 640 480];
            app.UIFigure.Name = 'MATLAB App';

            % Create RollButton
            app.RollButton = uibutton(app.UIFigure, 'push');
            app.RollButton.ButtonPushedFcn = createCallbackFcn(app, @RollButtonPushed, true);
            app.RollButton.BackgroundColor = [0 0 0];
            app.RollButton.FontName = 'Bodoni 72 Oldstyle';
            app.RollButton.FontSize = 24;
            app.RollButton.FontWeight = 'bold';
            app.RollButton.FontAngle = 'italic';
            app.RollButton.FontColor = [0.8 0.8 0.8];
            app.RollButton.Position = [188 11 185 53];
            app.RollButton.Text = 'Roll';

            % Create EndTurnButton
            app.EndTurnButton = uibutton(app.UIFigure, 'push');
            app.EndTurnButton.ButtonPushedFcn = createCallbackFcn(app, @EndTurnButtonPushed, true);
            app.EndTurnButton.BackgroundColor = [0 0 0];
            app.EndTurnButton.FontName = 'Bodoni 72 Oldstyle';
            app.EndTurnButton.FontSize = 24;
            app.EndTurnButton.FontWeight = 'bold';
            app.EndTurnButton.FontAngle = 'italic';
            app.EndTurnButton.FontColor = [0.8 0.8 0.8];
            app.EndTurnButton.Position = [17 11 114 53];
            app.EndTurnButton.Text = 'End Turn';

            % Create ZonkLabel
            app.ZonkLabel = uilabel(app.UIFigure);
            app.ZonkLabel.FontName = 'Optima';
            app.ZonkLabel.FontSize = 24;
            app.ZonkLabel.FontWeight = 'bold';
            app.ZonkLabel.FontAngle = 'italic';
            app.ZonkLabel.FontColor = [1 1 1];
            app.ZonkLabel.Position = [277 439 75 32];
            app.ZonkLabel.Text = 'Zonk!';

            % Create Image
            app.Image = uiimage(app.UIFigure);
            app.Image.Position = [495 190 137 239];
            app.Image.ImageSource = 'Screenshot 2023-03-10 at 12.29.15 AM.png';

            % Create Player1EditFieldLabel
            app.Player1EditFieldLabel = uilabel(app.UIFigure);
            app.Player1EditFieldLabel.BackgroundColor = [1 1 1];
            app.Player1EditFieldLabel.HorizontalAlignment = 'right';
            app.Player1EditFieldLabel.FontSize = 14;
            app.Player1EditFieldLabel.FontAngle = 'italic';
            app.Player1EditFieldLabel.Position = [10 439 56 32];
            app.Player1EditFieldLabel.Text = 'Player 1';

            % Create Player1EditField
            app.Player1EditField = uieditfield(app.UIFigure, 'numeric');
            app.Player1EditField.ValueChangedFcn = createCallbackFcn(app, @Player1EditFieldValueChanged, true);
            app.Player1EditField.FontSize = 14;
            app.Player1EditField.FontWeight = 'bold';
            app.Player1EditField.Position = [75 439 114 32];

            % Create Player2EditFieldLabel
            app.Player2EditFieldLabel = uilabel(app.UIFigure);
            app.Player2EditFieldLabel.BackgroundColor = [1 1 1];
            app.Player2EditFieldLabel.HorizontalAlignment = 'right';
            app.Player2EditFieldLabel.FontSize = 14;
            app.Player2EditFieldLabel.FontAngle = 'italic';
            app.Player2EditFieldLabel.Position = [458 439 59 32];
            app.Player2EditFieldLabel.Text = 'Player 2';

            % Create Player2EditField
            app.Player2EditField = uieditfield(app.UIFigure, 'numeric');
            app.Player2EditField.FontSize = 14;
            app.Player2EditField.FontWeight = 'bold';
            app.Player2EditField.Position = [525 439 100 32];

            % Create TotalValueEditFieldLabel
            app.TotalValueEditFieldLabel = uilabel(app.UIFigure);
            app.TotalValueEditFieldLabel.HorizontalAlignment = 'right';
            app.TotalValueEditFieldLabel.Position = [23 100 63 22];
            app.TotalValueEditFieldLabel.Text = 'Total Value';

            % Create TotalValueEditField
            app.TotalValueEditField = uieditfield(app.UIFigure, 'numeric');
            app.TotalValueEditField.FontWeight = 'bold';
            app.TotalValueEditField.FontAngle = 'italic';
            app.TotalValueEditField.Position = [101 100 100 22];

            % Create Dice3Label
            app.Dice3Label = uilabel(app.UIFigure);
            app.Dice3Label.HorizontalAlignment = 'right';
            app.Dice3Label.Position = [22 288 39 22];
            app.Dice3Label.Text = 'Dice 3';

            % Create Dice3EditField
            app.Dice3EditField = uieditfield(app.UIFigure, 'numeric');
            app.Dice3EditField.FontWeight = 'bold';
            app.Dice3EditField.Position = [76 288 50 22];

            % Create Dice2Label
            app.Dice2Label = uilabel(app.UIFigure);
            app.Dice2Label.HorizontalAlignment = 'right';
            app.Dice2Label.Position = [23 328 39 22];
            app.Dice2Label.Text = 'Dice 2';

            % Create Dice2EditField
            app.Dice2EditField = uieditfield(app.UIFigure, 'numeric');
            app.Dice2EditField.FontWeight = 'bold';
            app.Dice2EditField.Position = [77 328 49 22];

            % Create Dice1Label
            app.Dice1Label = uilabel(app.UIFigure);
            app.Dice1Label.HorizontalAlignment = 'right';
            app.Dice1Label.Position = [22 371 39 22];
            app.Dice1Label.Text = 'Dice 1';

            % Create Dice1EditField
            app.Dice1EditField = uieditfield(app.UIFigure, 'numeric');
            app.Dice1EditField.FontWeight = 'bold';
            app.Dice1EditField.Position = [76 371 50 22];

            % Create Dice4Label
            app.Dice4Label = uilabel(app.UIFigure);
            app.Dice4Label.HorizontalAlignment = 'right';
            app.Dice4Label.Position = [22 247 39 22];
            app.Dice4Label.Text = 'Dice 4';

            % Create Dice4EditField
            app.Dice4EditField = uieditfield(app.UIFigure, 'numeric');
            app.Dice4EditField.FontWeight = 'bold';
            app.Dice4EditField.Position = [76 247 50 22];

            % Create Dice5Label
            app.Dice5Label = uilabel(app.UIFigure);
            app.Dice5Label.HorizontalAlignment = 'right';
            app.Dice5Label.Position = [23 209 39 22];
            app.Dice5Label.Text = 'Dice 5';

            % Create Dice5EditField
            app.Dice5EditField = uieditfield(app.UIFigure, 'numeric');
            app.Dice5EditField.FontWeight = 'bold';
            app.Dice5EditField.Position = [77 209 49 22];

            % Create Dice6Label
            app.Dice6Label = uilabel(app.UIFigure);
            app.Dice6Label.HorizontalAlignment = 'right';
            app.Dice6Label.Position = [22 169 39 22];
            app.Dice6Label.Text = 'Dice 6';

            % Create Dice6EditField
            app.Dice6EditField = uieditfield(app.UIFigure, 'numeric');
            app.Dice6EditField.FontWeight = 'bold';
            app.Dice6EditField.Position = [76 169 50 22];

            % Create HoldDice3CheckBox
            app.HoldDice3CheckBox = uicheckbox(app.UIFigure);
            app.HoldDice3CheckBox.ValueChangedFcn = createCallbackFcn(app, @HoldDice3CheckBoxValueChanged, true);
            app.HoldDice3CheckBox.Text = 'Hold Dice 3';
            app.HoldDice3CheckBox.Position = [134 288 85 22];

            % Create HoldDice4CheckBox
            app.HoldDice4CheckBox = uicheckbox(app.UIFigure);
            app.HoldDice4CheckBox.ValueChangedFcn = createCallbackFcn(app, @HoldDice4CheckBoxValueChanged, true);
            app.HoldDice4CheckBox.Text = 'Hold Dice 4';
            app.HoldDice4CheckBox.Position = [134 247 85 22];

            % Create HoldDice5CheckBox
            app.HoldDice5CheckBox = uicheckbox(app.UIFigure);
            app.HoldDice5CheckBox.ValueChangedFcn = createCallbackFcn(app, @HoldDice5CheckBoxValueChanged, true);
            app.HoldDice5CheckBox.Text = 'Hold Dice 5';
            app.HoldDice5CheckBox.Position = [134 209 85 22];

            % Create HoldDice6CheckBox
            app.HoldDice6CheckBox = uicheckbox(app.UIFigure);
            app.HoldDice6CheckBox.ValueChangedFcn = createCallbackFcn(app, @HoldDice6CheckBoxValueChanged, true);
            app.HoldDice6CheckBox.Text = 'Hold Dice 6';
            app.HoldDice6CheckBox.Position = [134 169 85 22];

            % Create HoldDice2CheckBox
            app.HoldDice2CheckBox = uicheckbox(app.UIFigure);
            app.HoldDice2CheckBox.ValueChangedFcn = createCallbackFcn(app, @HoldDice2CheckBoxValueChanged, true);
            app.HoldDice2CheckBox.Text = 'Hold Dice 2';
            app.HoldDice2CheckBox.Position = [134 328 85 22];

            % Create HoldDice1CheckBox
            app.HoldDice1CheckBox = uicheckbox(app.UIFigure);
            app.HoldDice1CheckBox.ValueChangedFcn = createCallbackFcn(app, @HoldDice1CheckBoxValueChanged, true);
            app.HoldDice1CheckBox.Text = 'Hold Dice 1';
            app.HoldDice1CheckBox.Position = [134 371 85 22];

            % Create Image3
            app.Image3 = uiimage(app.UIFigure);
            app.Image3.Position = [318 288 165 140];
            app.Image3.ImageSource = fullfile(pathToMLAPP, 'dicethrowgif.gif');

            % Create Image4
            app.Image4 = uiimage(app.UIFigure);
            app.Image4.Position = [415 11 211 177];
            app.Image4.ImageSource = fullfile(pathToMLAPP, 'Screenshot 2023-03-13 at 8.32.57 PM.png');

            % Create WINNEREditFieldLabel
            app.WINNEREditFieldLabel = uilabel(app.UIFigure);
            app.WINNEREditFieldLabel.HorizontalAlignment = 'right';
            app.WINNEREditFieldLabel.FontName = 'Hiragino Sans GB';
            app.WINNEREditFieldLabel.FontSize = 20;
            app.WINNEREditFieldLabel.FontWeight = 'bold';
            app.WINNEREditFieldLabel.FontAngle = 'italic';
            app.WINNEREditFieldLabel.Position = [249 227 94 26];
            app.WINNEREditFieldLabel.Text = 'WINNER';

            % Create WINNEREditField
            app.WINNEREditField = uieditfield(app.UIFigure, 'text');
            app.WINNEREditField.FontName = 'Bodoni 72 Oldstyle';
            app.WINNEREditField.FontSize = 20;
            app.WINNEREditField.FontWeight = 'bold';
            app.WINNEREditField.FontAngle = 'italic';
            app.WINNEREditField.FontColor = [1 0 0];
            app.WINNEREditField.Position = [358 223 100 30];

            % Create Lamp1
            app.Lamp1 = uilamp(app.UIFigure);
            app.Lamp1.Visible = 'off';
            app.Lamp1.Position = [434 260 20 20];

            % Create Lamp2
            app.Lamp2 = uilamp(app.UIFigure);
            app.Lamp2.Visible = 'off';
            app.Lamp2.Position = [274 260 20 20];

            % Create Lamp3
            app.Lamp3 = uilamp(app.UIFigure);
            app.Lamp3.Visible = 'off';
            app.Lamp3.Position = [396 260 20 20];

            % Create Lamp4
            app.Lamp4 = uilamp(app.UIFigure);
            app.Lamp4.Visible = 'off';
            app.Lamp4.Position = [315 260 20 20];

            % Create Lamp5
            app.Lamp5 = uilamp(app.UIFigure);
            app.Lamp5.Visible = 'off';
            app.Lamp5.Position = [356 260 20 20];

            % Create Lamp6
            app.Lamp6 = uilamp(app.UIFigure);
            app.Lamp6.Visible = 'off';
            app.Lamp6.Position = [436 197 20 20];

            % Create Lamp7
            app.Lamp7 = uilamp(app.UIFigure);
            app.Lamp7.Visible = 'off';
            app.Lamp7.Position = [273 197 20 20];

            % Create Lamp8
            app.Lamp8 = uilamp(app.UIFigure);
            app.Lamp8.Visible = 'off';
            app.Lamp8.Position = [396 197 20 20];

            % Create Lamp9
            app.Lamp9 = uilamp(app.UIFigure);
            app.Lamp9.Visible = 'off';
            app.Lamp9.Position = [315 197 20 20];

            % Create Lamp10
            app.Lamp10 = uilamp(app.UIFigure);
            app.Lamp10.Visible = 'off';
            app.Lamp10.Position = [358 197 20 20];

            % Create Lamp11
            app.Lamp11 = uilamp(app.UIFigure);
            app.Lamp11.Visible = 'off';
            app.Lamp11.Position = [233 260 20 20];

            % Create Lamp12
            app.Lamp12 = uilamp(app.UIFigure);
            app.Lamp12.Visible = 'off';
            app.Lamp12.Position = [233 197 20 20];

            % Create Lamp13
            app.Lamp13 = uilamp(app.UIFigure);
            app.Lamp13.Visible = 'off';
            app.Lamp13.Position = [233 229 20 20];

            % Create Lamp14
            app.Lamp14 = uilamp(app.UIFigure);
            app.Lamp14.Visible = 'off';
            app.Lamp14.Position = [471 260 20 20];

            % Create Lamp15
            app.Lamp15 = uilamp(app.UIFigure);
            app.Lamp15.Visible = 'off';
            app.Lamp15.Position = [471 197 20 20];

            % Create Lamp16
            app.Lamp16 = uilamp(app.UIFigure);
            app.Lamp16.Visible = 'off';
            app.Lamp16.Position = [471 228 20 20];

            % Create SelectPlayerButtonGroup
            app.SelectPlayerButtonGroup = uibuttongroup(app.UIFigure);
            app.SelectPlayerButtonGroup.Title = 'Select Player';
            app.SelectPlayerButtonGroup.Position = [271 84 100 75];

            % Create Player1Button
            app.Player1Button = uiradiobutton(app.SelectPlayerButtonGroup);
            app.Player1Button.Text = 'Player 1';
            app.Player1Button.Position = [11 29 66 22];

            % Create Player2Button
            app.Player2Button = uiradiobutton(app.SelectPlayerButtonGroup);
            app.Player2Button.Text = 'Player 2';
            app.Player2Button.Position = [11 7 66 22];
            app.Player2Button.Value = true;

            % Show the figure after all components are created
            app.UIFigure.Visible = 'on';
        end
    end

    % App creation and deletion
    methods (Access = public)

        % Construct app
        function app = CoreAppNew

            runningApp = getRunningApp(app);

            % Check for running singleton app
            if isempty(runningApp)

                % Create UIFigure and components
                createComponents(app)

                % Register the app with App Designer
                registerApp(app, app.UIFigure)

                % Execute the startup function
                runStartupFcn(app, @startupFcn)
            else

                % Focus the running singleton app
                figure(runningApp.UIFigure)

                app = runningApp;
            end

            if nargout == 0
                clear app
            end
        end

        % Code that executes before app deletion
        function delete(app)

            % Delete UIFigure when app is deleted
            delete(app.UIFigure)
        end
    end
end
