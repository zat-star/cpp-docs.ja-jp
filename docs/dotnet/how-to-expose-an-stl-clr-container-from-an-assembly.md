---
title: "方法: アセンブリから STL/CLR コンテナーを公開する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STL/CLR コンテナー [STL/CLR]"
  - "STL/CLR, アセンブリ間の問題"
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 方法: アセンブリから STL/CLR コンテナーを公開する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`list` STL\/CLR などのコンテナーと `map` テンプレートは ref クラスとして実装されます。  C\+\+ テンプレートがコンパイル時にインスタンス化されるため、同じシグネチャが対応するが、別のアセンブリには 2 種類のテンプレート クラスは、実際には別の型。  これは、テンプレート クラスがアセンブリの境界を越えて使用できないことを意味します。  
  
 クロス アセンブリ共有を有効にするには、STL\/CLR のコンテナーの実装 <xref:System.Collections.Generic.ICollection%601>ジェネリック インターフェイス。  このジェネリック インターフェイスを使用して、ジェネリックは、C\+\+、C\#、および Visual Basic サポートするすべての言語では、STL\/CLR のコンテナーにアクセスできます。  
  
 ここでは、. C\+\+ アセンブリという `StlClrClassLibrary`で記述された複数の STL\/CLR のコンテナー要素を表示する方法を示します。  これは `StlClrClassLibrary`にアクセスするには、2 個のアセンブリを示します。  最初のアセンブリは、C\#、C\+\+、および 2 番目に書き込まれます。  
  
 アセンブリは両方とも C\+\+ で記述されている場合、`generic_container` の typedef を使用してコンテナーのジェネリック インターフェイスにアクセスできます。  たとえば、型 `cliext::vector<int>`のコンテナーが存在する場合、ジェネリック インターフェイス次の操作: `cliext::vector<int>::generic_container`。  同様に、`generic_iterator` の typedef を、のように使用して、ジェネリック インターフェイス上の反復子を取得する: `cliext::vector<int>::generic_iterator`。  
  
 これらの typedef が C\+\+ ヘッダー ファイルで宣言されているため、他の言語で記述されたアセンブリでは使用できません。  したがって、C\# または他の .NET 言語の `cliext::vector<int>` のジェネリック インターフェイスにアクセスするには、`System.Collections.Generic.ICollection<int>`。  このコレクションを反復処理するには、`foreach` ループを使用します。  
  
 次の表は、各 STL\/CLR のコンテナーを実装するジェネリック インターフェイスの一覧です。:  
  
|STL\/CLR のコンテナー|ジェネリック インターフェイス|  
|---------------------|---------------------|  
|dequeT\<\>|ICollectionT\<\>|  
|hash\_mapK\<、V\>|IDictionaryK\<、V\>|  
|hash\_multimapK\<、V\>|IDictionaryK\<、V\>|  
|hash\_multisetT\<\>|ICollectionT\<\>|  
|hash\_setT\<\>|ICollectionT\<\>|  
|listT\<\>|ICollectionT\<\>|  
|mapK\<、V\>|IDictionaryK\<、V\>|  
|multimapK\<、V\>|IDictionaryK\<、V\>|  
|multisetT\<\>|ICollectionT\<\>|  
|setT\<\>|ICollectionT\<\>|  
|vectorT\<\>|ICollectionT\<\>|  
  
> [!NOTE]
>  `queue`、`priority_queue`と `stack` のコンテナーが反復子をサポートしないため、ジェネリック インターフェイスを実装しないと、アクセスするアセンブリにすることはできません。  
  
## 例 1  
  
### 説明  
 この例では、プライベートな STL\/CLR のメンバー データを含む C\+\+.クラスを宣言します。  これは、クラスのメンバーのコレクションへのアクセスを許可するには、パブリック メソッドを宣言します。  これは、2 種類の方法で 1 と他の .NET クライアントの C\+\+ クライアントの 1 にします。  
  
### コード  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## 例 2  
  
### 説明  
 この例では、例 1.で宣言されたクラスを実装します。  このクラス ライブラリを使用するクライアントの場合は、DLL は、マニフェスト ファイルを埋め込むには、マニフェスト ツール **mt.exe** を使用します。  詳細については、コードのコメントを参照してください。  
  
 マニフェスト ツールと side\-by\-side アセンブリの詳細については、「[C\/C\+\+ 分離アプリケーションおよび side\-by\-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)」を参照してください。  
  
### コード  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## 例 3  
  
### 説明  
 この例では、例 1 および 2.で作成したクラス ライブラリを使用する C\+\+. C\+\+ クライアントを作成します。  このクライアントは、コンテナーを反復処理し、コンテンツを表示するために STL\/CLR のコンテナーの `generic_container` の typedef を使用します。  
  
### コード  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### 出力  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
## 例 4  
  
### 説明  
 この例では、例 1 および 2.で作成したクラス ライブラリを使用する C\# クライアントを作成します。  このクライアントは、コンテナーを反復処理し、コンテンツを表示するために STL\/CLR のコンテナーの <xref:System.Collections.Generic.ICollection%601> のメソッドを使用します。  
  
### コード  
  
```  
// CsConsoleApp.cs  
// compile with: /r:Microsoft.VisualC.STLCLR.dll /r:StlClrClassLibrary.dll /r:System.dll  
  
using System;  
using System.Collections.Generic;  
using StlClrClassLibrary;  
using cliext;  
  
namespace CsConsoleApp  
{  
    class Program  
    {  
        static int Main(string[] args)  
        {  
            StlClrClass theClass = new StlClrClass();  
  
            Console.WriteLine("cliext::deque contents:");  
            ICollection<char> iCollChar = theClass.GetDequeCs();  
            foreach (char c in iCollChar)  
            {  
                Console.WriteLine(c);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::list contents:");  
            ICollection<float> iCollFloat = theClass.GetListCs();  
            foreach (float f in iCollFloat)  
            {  
                Console.WriteLine(f);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::map contents:");  
            IDictionary<int, string> iDict = theClass.GetMapCs();  
            foreach (KeyValuePair<int, string> kvp in iDict)  
            {  
                Console.WriteLine("{0} {1}", kvp.Key, kvp.Value);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::set contents:");  
            ICollection<double> iCollDouble = theClass.GetSetCs();  
            foreach (double d in iCollDouble)  
            {  
                Console.WriteLine(d);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::vector contents:");  
            ICollection<int> iCollInt = theClass.GetVectorCs();  
            foreach (int i in iCollInt)  
            {  
                Console.WriteLine(i);  
            }  
            Console.WriteLine();  
  
            return 0;  
        }  
    }  
}  
```  
  
### 出力  
  
```  
cliext::deque contents:  
a  
b  
  
cliext::list contents:  
3.14159  
2.71828  
  
cliext::map contents:  
0 Hello  
1 World  
  
cliext::set contents:  
2.71828  
3.14159  
  
cliext::vector contents:  
10  
20  
```  
  
## 参照  
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)