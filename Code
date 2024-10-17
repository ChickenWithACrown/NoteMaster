using System;
using System.Collections.Generic;
using System.Linq;

public class NotesStore
{
    // Dictionary to store notes grouped by state
    private Dictionary<string, List<string>> notes;

    // Constructor to initialize the dictionary
    public NotesStore()
    {
        notes = new Dictionary<string, List<string>>()
        {
            { "completed", new List<string>() },
            { "active", new List<string>() },
            { "others", new List<string>() }
        };
    }

    // Method to add a note with a state and name
    public void AddNote(string state, string name)
    {
        if (string.IsNullOrEmpty(name))
        {
            throw new Exception("Name cannot be empty");
        }

        if (!notes.ContainsKey(state))
        {
            throw new Exception($"Invalid state {state}");
        }

        notes[state].Add(name);
    }

    // Method to get notes for a specific state
    public List<string> GetNotes(string state)
    {
        if (!notes.ContainsKey(state))
        {
            throw new Exception($"Invalid state {state}");
        }

        return notes[state];
    }
}

public class Solution
{
    public static void Main()
    {
        try
        {
            // Create the NotesStore object
            var notesStoreObj = new NotesStore();

            // Read the number of operations
            var n = int.Parse(Console.ReadLine());

            // Loop through operations
            for (var i = 0; i < n; i++)
            {
                var operationInfo = Console.ReadLine().Split(' ');
                try
                {
                    if (operationInfo[0] == "AddNote")
                    {
                        // Add note with state and name
                        string state = operationInfo[1];
                        string name = operationInfo.Length == 2 ? "" : operationInfo[2];
                        notesStoreObj.AddNote(state, name);
                    }
                    else if (operationInfo[0] == "GetNotes")
                    {
                        // Get and print notes for the state
                        var result = notesStoreObj.GetNotes(operationInfo[1]);
                        if (result.Count == 0)
                        {
                            Console.WriteLine("No Notes");
                        }
                        else
                        {
                            Console.WriteLine(string.Join(",", result));
                        }
                    }
                    else
                    {
                        Console.WriteLine("Invalid Parameter");
                    }
                }
                catch (Exception e)
                {
                    Console.WriteLine("Error: " + e.Message);
                }
            }
        }
        catch (Exception e)
        {
            Console.WriteLine("Error: " + e.Message);
        }
    }
}
