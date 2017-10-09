---
title: "右シフト | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: cee551dfd0dbac11110a945edee21af6636138bc
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="right-shifts"></a>右シフト
負の値の符号付き整数型の右シフトの結果  
  
 負の値を右へシフトすると、絶対値の 1/2 (切り捨て) になります。 たとえば、符号付きの `short` の値 -253 (16 進で 0xFF03、バイナリで 11111111 00000011) を右に 1 ビット シフトすると、-127 (16 進で 0xFF81、バイナリで 11111111 10000001) になります。 正の 253 を右にシフトすると +126 になります。  
  
 右シフトでは、符号付き整数型の符号ビットが保持されます。 符号付き整数を右にシフトすると、最上位ビットはセットされたままになります。 たとえば、0xF0000000 が符号付き `int` の場合、右にシフトすると 0xF8000000 になります。 負の `int` を右に 32 回シフトすると 0xFFFFFFFF になります。  
  
 符号なし整数を右にシフトすると、最上位ビットはクリアされます。 たとえば、0xF000 が符号なしの場合、結果は 0x7800 です。 `unsigned` または正の `int` を右に 32 回シフトすると、0x00000000 になります。  
  
## <a name="see-also"></a>関連項目  
 [整数](../c-language/integers.md)
