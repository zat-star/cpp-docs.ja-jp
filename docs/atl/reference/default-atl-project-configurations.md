---
title: "既定の ATL プロジェクトの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, default configurations
ms.assetid: 7e272722-41af-4330-b965-a6d74ec16880
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 41ab65c411bef478d063e5165d3167f58ace37d7
ms.lasthandoff: 02/24/2017

---
# <a name="default-atl-project-configurations"></a>ATL プロジェクトの既定の構成
このトピックでは、Visual C .NET で Visual C 6.0 の既定のプロジェクト構成での既定 ATL のプロジェクト構成を比較します。  
  
## <a name="visual-c-net-default-configurations"></a>Visual C .NET の既定の構成  
 Visual C .NET では、ATL プロジェクト ウィザードは、既定では、2 つのプロジェクト構成を作成します。  
  
### <a name="visual-c-net-configurations"></a>Visual C .NET 構成  
  
|構成|文字セット|ATL の使用|  
|-------------------|-------------------|----------------|  
|解放|MBCS|[DLL]|  
|デバッグ|MBCS|[DLL]|  
  
 **文字セット**、 **ATL の使用**をすべて変更可能で、**プロジェクト設定** ダイアログ ボックス 、**全般** タブをクリックします。 Configuration Manager を使用して、独自の構成を追加することもできます。 詳細については、「[ビルド構成](/visualstudio/ide/understanding-build-configurations)します。  
  
## <a name="version-60-default-configurations"></a>バージョン 6.0 の既定の構成  
 Visual c バージョン 6.0 では、(ここでは、ATL プロジェクト ウィザードと呼ばれます)、ATL COM AppWizard は既定で 6 つのプロジェクト構成を作成します。 構成では、リリース、デバッグ、Unicode、および CRT と ATL の設定の使用のバリエーションをでした。 必要な場合、Configuration Manager を使用して Visual C .NET でこれらすべての構成を複製できます。  
  
### <a name="version-60-configurations"></a>バージョン 6.0 の構成  
  
|構成|文字セット|ATL の使用|  
|-------------------|-------------------|----------------|  
|デバッグ|MBCS|スタティック|  
|Unicode をデバッグします。|UNICODE|スタティック|  
|リリースの最小の依存関係|MBCS|スタティック|  
|最小の依存関係の Unicode をリリースします。|UNICODE|スタティック|  
|リリースの最小サイズ|MBCS|[DLL]|  
|最小サイズの Unicode をリリースします。|UNICODE|[DLL]|  
  
## <a name="see-also"></a>関連項目  
 [ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [プロジェクトのプロパティの使用](../../ide/working-with-project-properties.md)   
 [構成マネージャー ダイアログ ボックス](http://msdn.microsoft.com/en-us/fa182dca-282e-4ae5-bf37-e155344ca18b)   
 [コードのコンパイルとビルド](/visualstudio/ide/compiling-and-building-in-visual-studio)


