---
title: "方法: ADO.NET の BSTR 文字列をマーシャリングする (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ADO.NET [C++], マーシャリング (BSTR 文字列を)"
  - "BSTR, 文字列"
  - "文字列 [C++], マーシャリング (BSTR 文字列を)"
ms.assetid: 5daf4d9e-6ae8-4604-908f-855e37c8d636
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: ADO.NET の BSTR 文字列をマーシャリングする (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

データベースに COM 文字列 \(`BSTR`\) を追加する方法、およびデータベースの <xref:System.String?displayProperty=fullName> を `BSTR` にマーシャリングする方法について説明します。  
  
## 使用例  
 この例では、ADO.NET <xref:System.Data.DataTable> オブジェクトとやり取りするための DatabaseClass というクラスが作成されます。  このクラスはネイティブな C\+\+ `class` です \(`ref class` や `value class` とは異なります\)。  これは、ネイティブ コードからこのクラスを使用するために必要なもので、マネージ型をネイティブ コードで使用することはできません。  このクラスは、クラスの宣言の前に `#pragma managed` ディレクティブが付いていることからわかるように、CLR を対象としてコンパイルされます。  このディレクティブの詳細については、「[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。  
  
 DatabaseClass クラスのプライベート メンバーは `gcroot<DataTable ^> table` です。  ネイティブ型にはマネージ型は含まれないため、`gcroot` キーワードが必要です。  `gcroot` の詳細については、「[方法: ネイティブ型のハンドルを宣言する](../dotnet/how-to-declare-handles-in-native-types.md)」を参照してください。  
  
 この例のコードの他の部分は、`#pragma unmanaged` ディレクティブが `main` の前についていることからわかるように、ネイティブな C\+\+ コードです。  この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出し、テーブルを作成してテーブルのいくつかの行を設定します。  COM 文字列は、データベース列 StringCol の値として渡されます。  DatabaseClass 内では、<xref:System.Runtime.InteropServices?displayProperty=fullName> 名前空間にあるマーシャリング機能を使用して、これらの文字列がマネージ文字列にマーシャリングされます。  具体的には、<xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> メソッドは `BSTR` を <xref:System.String> にマーシャリングするときに、また <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> メソッドは <xref:System.String> を `BSTR` にマーシャリングするときに使用されます。  
  
> [!NOTE]
>  <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> によって割り当てられたメモリは、<xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> または `SysFreeString` を呼び出して解放する必要があります。  
  
```  
// adonet_marshal_string_bstr.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(BSTR stringColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["StringCol"] = Marshal::PtrToStringBSTR(  
            (IntPtr)stringColValue);  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("StringCol",  
            Type::GetType("System.String"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(BSTR dataColumn, BSTR *values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringBSTR(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed string  
            // to a BSTR.  
            values[i] = (BSTR)Marshal::StringToBSTR(  
                (String ^)rows[i][columnStr]).ToPointer();  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
  
    BSTR str1 = SysAllocString(L"This is string 1.");  
    db->AddRow(str1);  
  
    BSTR str2 = SysAllocString(L"This is string 2.");  
    db->AddRow(str2);  
  
    // Now retrieve the rows and display their contents.  
    BSTR values[MAXCOLS];  
    BSTR str3 = SysAllocString(L"StringCol");  
    int len = db->GetValuesForColumn(  
        str3, values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        wcout << "StringCol: " << values[i] << endl;  
  
        // Deallocate the memory allocated using  
        // Marshal::StringToBSTR.  
        SysFreeString(values[i]);  
    }  
  
    SysFreeString(str1);  
    SysFreeString(str2);  
    SysFreeString(str3);  
    delete db;  
  
    return 0;  
}  
```  
  
  **StringCol: This is string 1.**  
**StringCol: This is string 2.**   
## コードのコンパイル  
  
-   コマンド ラインからコードをコンパイルするには、コード例を adonet\_marshal\_string\_native.cpp というファイルに保存し、次のステートメントを入力します。  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp  
    ```  
  
## .NET Framework セキュリティ  
 ADO.NET に関するセキュリティの詳細については、「[ADO.NET アプリケーションのセキュリティ保護](../Topic/Securing%20ADO.NET%20Applications.md)」を参照してください。  
  
## 参照  
 <xref:System.Runtime.InteropServices>   
 [データ アクセス](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](http://msdn.microsoft.com/ja-jp/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [ネイティブと .NET の相互運用性](../Topic/Native%20and%20.NET%20Interoperability.md)