import json
import os
import pickle
try:
    path = os.mkdir("NEW_FOLDER")
except:
    pass

if os.path.exists("NEW_FOLDER/newFile.txt"):
    with open("NEW_FOLDER/newFile.txt","rb") as f:
        dat = f.read()
        try:
            newDict = pickle.loads(dat)
        except:
            newDict = {}
else:
    f = open("NEW_FOLDER/newFile.txt",'ab')
    f.close()
    newDict = {}

while(True):
    print("")
    print("Enter 1 to Create")
    print("Enter 2 to Read")
    print("Enter 3 to Delete")
    print("Enter 4 to stop")
    while(True):
        try:
            ch = int(input("Enter any choice: "))
            if ch>0 and ch<5:
                break
            else:
                print("Enter valid choice")
        except:
            print("Enter valid choice")
    if ch == 1:
        key = input("Enter key: ")
        if newDict.get(key) == None:
            while(True):
                value = input("Enter value(Json object) :" )
                try:
                    if json.loads(value):
                        break
                except:
                    print("Not a Valid Json Object, please enter valid json object")
            newDict[key] = value
            with open("NEW_FOLDER/newFile.txt",'wb') as f:
                pickle.dump(newDict,f)
            print("Succesfully created")
        else:
            print("The key already exists")
    if ch == 2:
        if not newDict:
            print("The File is Empty, Please create one, before reading")
        else:
            key = input("Enter key to read: ")
            if newDict.get(key) == None:
                print("Key Not Found")
            else:
                print(json.loads(newDict.get(key)))

    if ch == 3:
        if not newDict:
            print("The File is Empty, Please create one, before Deleting")
        else:
            key = input("Enter key to delete: ")
            if newDict.get(key) == None:
                print("Key Not Found")
            else:
                newDict.pop(key)
                with open("NEW_FOLDER/newFile.txt",'wb') as f:
                    pickle.dump(newDict,f)
                print("Succesfully deleted")
    if ch == 4:
        break
