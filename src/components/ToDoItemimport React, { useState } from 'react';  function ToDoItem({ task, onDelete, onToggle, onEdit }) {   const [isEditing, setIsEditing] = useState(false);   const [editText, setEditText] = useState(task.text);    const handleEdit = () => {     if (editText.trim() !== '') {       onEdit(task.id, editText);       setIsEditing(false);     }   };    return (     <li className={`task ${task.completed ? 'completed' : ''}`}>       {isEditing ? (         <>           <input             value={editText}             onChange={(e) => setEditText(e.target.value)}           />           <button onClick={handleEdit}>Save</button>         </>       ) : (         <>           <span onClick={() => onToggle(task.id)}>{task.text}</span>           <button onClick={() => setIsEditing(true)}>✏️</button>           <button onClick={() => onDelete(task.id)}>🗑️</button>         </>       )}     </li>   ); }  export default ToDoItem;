import React, { useState } from 'react';

function ToDoItem({ task, onDelete, onToggle, onEdit }) {
  const [isEditing, setIsEditing] = useState(false);
  const [editText, setEditText] = useState(task.text);

  const handleEdit = () => {
    if (editText.trim() !== '') {
      onEdit(task.id, editText);
      setIsEditing(false);
    }
  };

  return (
    <li className={`task ${task.completed ? 'completed' : ''}`}>
      {isEditing ? (
        <>
          <input
            value={editText}
            onChange={(e) => setEditText(e.target.value)}
          />
          <button onClick={handleEdit}>Save</button>
        </>
      ) : (
        <>
          <span onClick={() => onToggle(task.id)}>{task.text}</span>
          <button onClick={() => setIsEditing(true)}>✏️</button>
          <button onClick={() => onDelete(task.id)}>🗑️</button>
        </>
      )}
    </li>
  );
}

export default ToDoItem;
