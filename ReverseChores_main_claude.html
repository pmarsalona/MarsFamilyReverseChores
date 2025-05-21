import React, { useState, useEffect } from 'react';
import { User, UserPlus, Settings, Check, X, Plus, Trash2, RefreshCw, Edit2, Save } from 'lucide-react';

// Default profile colors
const PROFILE_COLORS = ["#FF6B6B", "#48BEFF", "#9F7AEA"];

const App = () => {
  // Load data from localStorage or use defaults
  const loadFromStorage = () => {
    const saved = localStorage.getItem('choreTracker');
    if (saved) return JSON.parse(saved);
    
    // Default data for first run
    return {
      kids: [
        {
          id: 1,
          name: "Penelope",
          baseAllowance: 1.00,
          color: PROFILE_COLORS[0],
          chores: [
            { id: 1, name: "Make bed", deduction: 0.05, missCount: 0 },
            { id: 2, name: "Feed pet", deduction: 0.10, missCount: 0 }
          ]
        },
        {
          id: 2,
          name: "Amelia",
          baseAllowance: 1.00,
          color: PROFILE_COLORS[1],
          chores: [
            { id: 1, name: "Clean room", deduction: 0.10, missCount: 0 },
            { id: 2, name: "Put away toys", deduction: 0.05, missCount: 0 }
          ]
        },
        {
          id: 3,
          name: "Lena",
          baseAllowance: 1.00,
          color: PROFILE_COLORS[2],
          chores: [
            { id: 1, name: "Help set table", deduction: 0.05, missCount: 0 },
            { id: 2, name: "Put dishes away", deduction: 0.10, missCount: 0 }
          ]
        }
      ]
    };
  };

  const [data, setData] = useState(loadFromStorage);
  const [activeKid, setActiveKid] = useState(0);
  const [newChore, setNewChore] = useState({ name: "", deduction: 0.05 });
  const [editMode, setEditMode] = useState(false);

  // Save to localStorage whenever data changes
  useEffect(() => {
    localStorage.setItem('choreTracker', JSON.stringify(data));
  }, [data]);

  // Calculate current allowance based on missed chores
  const calculateAllowance = (kid) => {
    const totalDeductions = kid.chores
      .reduce((total, chore) => total + (chore.deduction * chore.missCount), 0);
    
    return Math.max(0, kid.baseAllowance - totalDeductions).toFixed(2);
  };

  // Increment miss count for a chore
  const incrementMiss = (choreId) => {
    setData(prev => {
      const newData = {...prev};
      const kid = newData.kids[activeKid];
      const choreIndex = kid.chores.findIndex(c => c.id === choreId);
      
      if (choreIndex !== -1) {
        kid.chores[choreIndex].missCount += 1;
      }
      
      return newData;
    });
  };

  // Decrement miss count for a chore
  const decrementMiss = (choreId) => {
    setData(prev => {
      const newData = {...prev};
      const kid = newData.kids[activeKid];
      const choreIndex = kid.chores.findIndex(c => c.id === choreId);
      
      if (choreIndex !== -1 && kid.chores[choreIndex].missCount > 0) {
        kid.chores[choreIndex].missCount -= 1;
      }
      
      return newData;
    });
  };

  // Add a new chore
  const addChore = () => {
    if (!newChore.name.trim()) return;
    
    setData(prev => {
      const newData = {...prev};
      const kid = newData.kids[activeKid];
      
      // Get highest ID and add 1
      const newId = kid.chores.length ? Math.max(...kid.chores.map(c => c.id)) + 1 : 1;
      
      kid.chores.push({
        id: newId,
        name: newChore.name.trim(),
        deduction: parseFloat(newChore.deduction) || 0.05,
        missCount: 0
      });
      
      return newData;
    });
    
    setNewChore({ name: "", deduction: 0.05 });
  };

  // Delete a chore
  const deleteChore = (choreId) => {
    setData(prev => {
      const newData = {...prev};
      const kid = newData.kids[activeKid];
      kid.chores = kid.chores.filter(c => c.id !== choreId);
      return newData;
    });
  };

  // Reset all chores for the week
  const resetWeek = () => {
    if (window.confirm("Reset all chores for the new week?")) {
      setData(prev => {
        const newData = {...prev};
        newData.kids.forEach(kid => {
          kid.chores.forEach(chore => {
            chore.missCount = 0;
          });
        });
        return newData;
      });
    }
  };

  // Save edited kid data
  const saveKidData = () => {
    setEditMode(false);
  };

  // Update kid name
  const updateKidName = (name) => {
    setData(prev => {
      const newData = {...prev};
      newData.kids[activeKid].name = name;
      return newData;
    });
  };

  // Update allowance
  const updateAllowance = (amount) => {
    setData(prev => {
      const newData = {...prev};
      newData.kids[activeKid].baseAllowance = parseFloat(amount) || 1.00;
      return newData;
    });
  };

  // Format currency
  const formatCurrency = (amount) => {
    return `$${parseFloat(amount).toFixed(2)}`;
  };

  return (
    <div className="flex flex-col min-h-screen bg-gray-50">
      {/* Header */}
      <header className="bg-white shadow p-4 flex justify-between items-center">
        <h1 className="text-xl font-bold text-gray-800">Kids Chore Tracker</h1>
        <div className="flex space-x-2">
          <button 
            onClick={resetWeek}
            className="flex items-center gap-1 bg-blue-100 hover:bg-blue-200 text-blue-700 px-3 py-2 rounded-lg"
          >
            <RefreshCw size={16} />
            <span className="hidden sm:inline">Reset Week</span>
          </button>
        </div>
      </header>

      {/* Kid Tabs */}
      <div className="flex overflow-x-auto bg-white shadow-sm mb-1">
        {data.kids.map((kid, index) => (
          <button
            key={kid.id}
            onClick={() => setActiveKid(index)}
            className={`flex items-center gap-2 py-3 px-4 flex-shrink-0 transition-colors border-b-2 ${
              activeKid === index ? 'border-blue-500 text-blue-600' : 'border-transparent text-gray-600 hover:bg-gray-50'
            }`}
          >
            <div 
              className="w-8 h-8 rounded-full flex items-center justify-center text-white"
              style={{ backgroundColor: kid.color }}
            >
              {kid.name.charAt(0)}
            </div>
            <span>{kid.name}</span>
          </button>
        ))}
      </div>

      {/* Main Content */}
      <main className="flex-1 p-4">
        {data.kids[activeKid] && (
          <div className="max-w-md mx-auto">
            {/* Kid Profile */}
            <div className="bg-white rounded-lg shadow p-4 mb-4">
              <div className="flex items-center justify-between mb-3">
                <div className="flex items-center gap-3">
                  <div 
                    className="w-12 h-12 rounded-full flex items-center justify-center text-white text-xl"
                    style={{ backgroundColor: data.kids[activeKid].color }}
                  >
                    {data.kids[activeKid].name.charAt(0)}
                  </div>
                  {!editMode ? (
                    <div>
                      <h2 className="text-xl font-bold">{data.kids[activeKid].name}</h2>
                      <p className="text-gray-600">Base Allowance: {formatCurrency(data.kids[activeKid].baseAllowance)}/week</p>
                    </div>
                  ) : (
                    <div className="flex flex-col gap-2">
                      <input 
                        type="text" 
                        value={data.kids[activeKid].name}
                        onChange={(e) => updateKidName(e.target.value)}
                        className="border rounded p-1 text-lg"
                      />
                      <div className="flex items-center">
                        <span className="mr-2">Allowance:</span>
                        <input 
                          type="number" 
                          value={data.kids[activeKid].baseAllowance}
                          onChange={(e) => updateAllowance(e.target.value)}
                          min="0"
                          step="0.01"
                          className="border rounded p-1 w-16"
                        />
                        <span className="ml-1">/week</span>
                      </div>
                    </div>
                  )}
                </div>
                <button 
                  onClick={() => editMode ? saveKidData() : setEditMode(true)}
                  className="p-2 text-gray-500 hover:text-gray-700 hover:bg-gray-100 rounded-full"
                >
                  {editMode ? <Save size={20} /> : <Edit2 size={20} />}
                </button>
              </div>

              <div className="flex justify-between items-center mb-2 p-3 bg-gray-50 rounded-lg">
                <div>
                  <h3 className="font-medium">Current Allowance:</h3>
                  <div className="text-gray-500 text-sm">After deductions</div>
                </div>
                <div className="text-2xl font-bold">
                  {formatCurrency(calculateAllowance(data.kids[activeKid]))}
                </div>
              </div>
            </div>

            {/* Chores List */}
            <div className="bg-white rounded-lg shadow">
              <div className="p-4 border-b">
                <h3 className="font-bold">Chores</h3>
                <p className="text-gray-500 text-sm">Click a chore to mark it as skipped</p>
              </div>
              
              <ul className="divide-y">
                {data.kids[activeKid].chores.map((chore) => (
                  <li key={chore.id} className="p-3 hover:bg-gray-50">
                    <div className="flex items-center justify-between">
                      <div className="flex-1">
                        <p className="font-medium">{chore.name}</p>
                        <p className="text-xs text-gray-500">
                          Deduction: {formatCurrency(chore.deduction)} per miss
                        </p>
                      </div>
                      <div className="flex items-center space-x-1">
                        <button 
                          onClick={() => decrementMiss(chore.id)}
                          className="p-1 text-gray-500 hover:text-gray-700 bg-gray-100 hover:bg-gray-200 rounded"
                          disabled={chore.missCount === 0}
                        >
                          -
                        </button>
                        <div className="w-8 text-center">
                          <span className={`${chore.missCount > 0 ? 'text-red-500 font-bold' : 'text-gray-500'}`}>
                            {chore.missCount}
                          </span>
                        </div>
                        <button 
                          onClick={() => incrementMiss(chore.id)}
                          className="p-1 text-gray-500 hover:text-gray-700 bg-gray-100 hover:bg-gray-200 rounded"
                        >
                          +
                        </button>
                        <div className="ml-2 text-red-500 font-medium">
                          {chore.missCount > 0 ? `-${formatCurrency(chore.deduction * chore.missCount)}` : ''}
                        </div>
                        <button 
                          onClick={() => deleteChore(chore.id)}
                          className="p-2 text-gray-400 hover:text-red-500 rounded-full"
                        >
                          <Trash2 size={16} />
                        </button>
                      </div>
                    </div>
                  </li>
                ))}
              </ul>

              {/* Add New Chore */}
              <div className="p-4 border-t">
                <h4 className="text-sm font-medium text-gray-500 mb-2">Add New Chore</h4>
                <div className="flex space-x-2">
                  <input
                    type="text"
                    value={newChore.name}
                    onChange={(e) => setNewChore({...newChore, name: e.target.value})}
                    placeholder="Chore name"
                    className="flex-1 border rounded-lg p-2 text-sm"
                  />
                  <div className="relative">
                    <span className="absolute left-3 top-2.5 text-gray-500">$</span>
                    <input
                      type="number"
                      value={newChore.deduction}
                      onChange={(e) => setNewChore({...newChore, deduction: e.target.value})}
                      min="0.01"
                      step="0.01"
                      className="w-20 border rounded-lg p-2 pl-6 text-sm"
                    />
                  </div>
                  <button
                    onClick={addChore}
                    className="bg-blue-500 hover:bg-blue-600 text-white rounded-lg px-3 py-2"
                  >
                    <Plus size={20} />
                  </button>
                </div>
              </div>
            </div>
          </div>
        )}
      </main>

      <footer className="text-center p-4 text-gray-500 text-sm">
        <p>Kids Chore Tracker • {new Date().getFullYear()}</p>
      </footer>
    </div>
  );
};

export default App;