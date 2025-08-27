import React, { useState } from 'react';
import { FiSearch } from 'react-icons/fi';

const SearchBar = () => {
  const [searchQuery, setSearchQuery] = useState('');

  const handleSearch = (e: React.FormEvent) => {
    e.preventDefault();
    // 这里添加搜索逻辑
    console.log('搜索:', searchQuery);
  };

  return (
    <form onSubmit={handleSearch} className="max-w-md mx-auto my-4">
      <div className="relative flex items-center">
        <input
          type="text"
          value={searchQuery}
          onChange={(e) => setSearchQuery(e.target.value)}
          placeholder="搜索..."
          className="w-full px-4 py-2 text-gray-700 bg-white border rounded-lg focus:border-blue-400 focus:outline-none focus:ring focus:ring-blue-300 focus:ring-opacity-40"
        />
        <button
          type="submit"
          className="absolute right-2 p-2 text-gray-600 hover:text-blue-500"
        >
          <FiSearch size={20} />
        </button>
      </div>
    </form>
  );
};

export default SearchBar;