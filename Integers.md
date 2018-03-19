-----------------------------------------------------------------------------------------
-- Created by: Aayman Shameem
-- Created on: Mar 19 2018
-- 
-- This code will tell the user if the number is positive or negative
-----------------------------------------------------------------------------------------
-- the title on the top
local titleText = display.newText( "Type in number", display.contentCenterX, display.contentCenterY - 488, native.systemFont, 177 )

local moreText = display.newText( "Number is: ", display.contentCenterX - 570, display.contentCenterY + 458, native.systemFont, 177 )

-- the text field for the user's input
local numberInput = native.newTextField( display.contentCenterX, display.contentCenterY - 177, 720, 277 )
numberInput.id = "The user's input"

-- the button of integers
local integerButton = display.newImageRect( "./assets/sprites/enterButton.png", 675, 277 )
integerButton.x = display.contentCenterX 
integerButton.y = display.contentCenterY + 177
integerButton.id = "the integer button"



local function Buttonteger( event )
	-- the two clears that will make sure that the text will not overlap
	local clear2 = display.newRect(display.contentCenterX + 277, display.contentCenterY + 458, 720, 200)
	clear2:setFillColor( 0, 0, 0 )

	local clear1 = display.newRect(display.contentCenterX + 277, display.contentCenterY + 458, 277, 180)
	clear1:setFillColor( 0, 0, 0 )

	local realNumber = tonumber(numberInput.text)

	-- if the number is positive, then show "Positive"
	if realNumber > 0 then
		local positiveText = display.newText( "Positive", display.contentCenterX + 277, display.contentCenterY + 458, native.systemFont, 177 ) 
	end

	-- if number is negative, then show "Negative"
	if realNumber < 0 then
		local NegativeText = display.newText( "Negative", display.contentCenterX + 277, display.contentCenterY + 458, native.systemFont, 177 )
	end

	-- if the number is 0, then show "Neutral"
	if realNumber == 0 then 
		local NeutralText = display.newText( "Neutral", display.contentCenterX + 277, display.contentCenterY + 458, native.systemFont, 177 )
	end

	-- if there is no value, then show "THERE MUST BE A NUMBER!!!"
	if realNumber == nil then
		local errorText = display.newText( "THERE MUST BE A NUMBER!!!", display.contentCenterX + 277, display.contentCenterY + 458, native.systemFont, 177 )
	end


end

integerButton:addEventListener( "touch", Buttonteger )
