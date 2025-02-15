---
title: Check if a variable is numeric | Microsoft Docs
description: Check if a variable is numeric	
author: georgiostrantzas
ms.service: power-automate
ms.subservice: desktop-flow
ms.topic: article
ms.date: 07/13/2021
ms.author: v-gtrantzas
ms.reviewer:
search.app: 
  - Flow
search.audienceType: 
  - flowmaker
  - enduser
---

# Check if a variable is numeric

Power Automate Desktop enables users to insert data into flows using message boxes. In some scenarios, you may want to ensure that the entered data are numbers to make your flow robust to unexpected failures.

To check whether a variable contains a number or not:

1. Use the **Set variable** action to create a new variable that indicates whether the variable you want to check contains a number or not. Initialize this variable to **true**. In the following example, the created variable is named **IsNumber**.

    ![The configured Set variable action.](media/check-if-variable-numeric/set-variable-action.png)

1. Deploy the **Convert text to number** action and configure it to convert the variable you want to check to number.

    ![The configured Convert text to number action.](media/check-if-variable-numeric/convert-text-number-action.png)

1. Select the **On error** option in the action, and create a new rule that sets the **IsNumber** variable to false every time the action fails. Additionally, configure the flow to continue running when an error occurs.

    ![The on error configuration of the Convert text to number action.](media/check-if-variable-numeric/convert-text-number-action-on-error.png)

1. Now, you can use conditionals to implement different behavior depending on the value of the **IsNumber** variable.

    ![An if - else block that checks the value of the IsNumber variable.](media/check-if-variable-numeric/conditionals.png)