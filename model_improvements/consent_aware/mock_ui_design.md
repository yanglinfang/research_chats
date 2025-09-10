import React from "react";

export default function ConsentAwareRoutingUI() {
  return (
    <div className="p-6 bg-gray-50 min-h-screen font-sans">
      {/* Header */}
      <div className="flex items-center justify-between bg-white shadow-md rounded-xl p-4 mb-6">
        <h1 className="text-xl font-semibold">Chat Session</h1>
        <div className="flex items-center space-x-2">
          <span className="text-sm text-gray-500">Active Model:</span>
          <span className="px-2 py-1 text-sm font-medium bg-blue-100 text-blue-700 rounded-lg">
            GPT-5 (Creative)
          </span>
        </div>
      </div>

      {/* Chat Window */}
      <div className="bg-white rounded-xl shadow p-4 h-[400px] overflow-y-auto mb-6">
        <div className="space-y-4">
          <div className="p-3 bg-blue-50 rounded-lg text-sm w-fit max-w-[80%]">
            User: Can you write me a poem?
          </div>
          <div className="p-3 bg-gray-100 rounded-lg text-sm w-fit max-w-[80%] ml-auto">
            GPT-5: Sure! Here’s a short one...
          </div>
          {/* Banner: Model switch notification */}
          <div className="bg-yellow-50 border-l-4 border-yellow-400 p-3 rounded-md text-sm flex justify-between items-center">
            <span>
              Switched to <strong>GPT-mini (Faster)</strong> for this task.
            </span>
            <div className="space-x-2">
              <button className="px-3 py-1 text-xs bg-gray-200 rounded-md hover:bg-gray-300">
                Undo
              </button>
              <button className="px-3 py-1 text-xs bg-blue-100 text-blue-700 rounded-md hover:bg-blue-200">
                Always use GPT-5
              </button>
            </div>
          </div>
        </div>
      </div>

      {/* Control Panel */}
      <div className="bg-white rounded-xl shadow p-4">
        <h2 className="font-medium mb-3">Consent-Aware Settings</h2>
        <div className="space-y-2 text-sm">
          <label className="flex items-center space-x-2">
            <input type="checkbox" defaultChecked />
            <span>Always ask before switching models</span>
          </label>
          <label className="flex items-center space-x-2">
            <input type="checkbox" />
            <span>Auto-switch only for speed improvements</span>
          </label>
          <label className="flex items-center space-x-2">
            <input type="checkbox" />
            <span>Lock this chat to current model (GPT-5)</span>
          </label>
        </div>
      </div>
    </div>
  );
}
