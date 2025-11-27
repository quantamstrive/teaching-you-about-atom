import React, { useState } from 'react';
import { Atom, Zap, Circle, Layers } from 'lucide-react';

export default function AtomExplorer() {
  const [activeSection, setActiveSection] = useState('intro');
  const [hoveredPart, setHoveredPart] = useState(null);

  const sections = {
    intro: {
      title: 'THE ATOM',
      content: 'The fundamental building block of all matter in the universe. Every solid, liquid, and gas is composed of atoms.',
      icon: Atom
    },
    structure: {
      title: 'ATOMIC STRUCTURE',
      content: 'Atoms consist of a dense nucleus containing protons and neutrons, surrounded by a cloud of electrons in orbital shells.',
      icon: Layers
    },
    particles: {
      title: 'SUBATOMIC PARTICLES',
      content: 'Protons carry positive charge, electrons carry negative charge, and neutrons are electrically neutral.',
      icon: Circle
    },
    energy: {
      title: 'ENERGY LEVELS',
      content: 'Electrons orbit the nucleus in specific energy levels. When they jump between levels, they absorb or emit energy as light.',
      icon: Zap
    }
  };

  const atomParts = [
    { id: 'nucleus', name: 'NUCLEUS', desc: 'Dense core containing protons & neutrons', color: 'bg-red-500' },
    { id: 'electron', name: 'ELECTRONS', desc: 'Negatively charged particles in orbit', color: 'bg-blue-500' },
    { id: 'proton', name: 'PROTONS', desc: 'Positively charged particles in nucleus', color: 'bg-yellow-500' },
    { id: 'neutron', name: 'NEUTRONS', desc: 'Neutral particles in nucleus', color: 'bg-gray-400' }
  ];

  return (
    <div className="min-h-screen bg-black text-white overflow-hidden relative">
      {/* Animated background shapes */}
      <div className="absolute inset-0 overflow-hidden pointer-events-none">
        <div className="absolute top-20 left-10 w-64 h-64 bg-gray-800 opacity-20 transform rotate-45 transition-all duration-1000 hover:rotate-90 hover:scale-110"></div>
        <div className="absolute bottom-20 right-20 w-96 h-96 bg-gray-700 opacity-15 transform -rotate-12 transition-all duration-1000 hover:rotate-12 hover:scale-110"></div>
        <div className="absolute top-1/2 left-1/3 w-48 h-48 bg-gray-600 opacity-10 transform rotate-90 transition-all duration-1000 hover:rotate-180 hover:scale-110"></div>
        <div className="absolute bottom-40 left-20 w-72 h-72 bg-gray-800 opacity-20 transform -rotate-45 transition-all duration-1000 hover:-rotate-90 hover:scale-110"></div>
      </div>

      {/* Main content */}
      <div className="relative z-10 container mx-auto px-8 py-12">
        {/* Header */}
        <div className="text-center mb-16 transform transition-all duration-700">
          <div className="inline-block p-6 bg-gray-900 transform rotate-2 transition-all duration-500 hover:rotate-0 hover:scale-105">
            <h1 className="text-7xl font-black tracking-wider">ATOMIC THEORY</h1>
            <div className="h-2 w-full bg-gradient-to-r from-blue-500 via-purple-500 to-red-500 mt-4 transform transition-all duration-500"></div>
          </div>
        </div>

        {/* Navigation Sections */}
        <div className="grid grid-cols-4 gap-6 mb-16">
          {Object.entries(sections).map(([key, section]) => {
            const Icon = section.icon;
            return (
              <button
                key={key}
                onClick={() => setActiveSection(key)}
                className={`p-6 transform transition-all duration-500 hover:scale-110 hover:-translate-y-2 ${
                  activeSection === key 
                    ? 'bg-white text-black rotate-0' 
                    : 'bg-gray-900 text-white rotate-1 hover:rotate-0'
                }`}
              >
                <Icon className="w-12 h-12 mx-auto mb-4" />
                <h3 className="font-black text-sm tracking-wider">{section.title}</h3>
              </button>
            );
          })}
        </div>

        {/* Active Section Content */}
        <div className="mb-16 bg-gray-900 p-8 transform -rotate-1 transition-all duration-700 hover:rotate-0">
          <div className="transform rotate-1">
            <h2 className="text-4xl font-black mb-6 tracking-wide">{sections[activeSection].title}</h2>
            <p className="text-xl text-gray-300 leading-relaxed">{sections[activeSection].content}</p>
          </div>
        </div>

        {/* Interactive Atom Model */}
        <div className="grid grid-cols-2 gap-12 items-center">
          <div className="relative h-96 flex items-center justify-center">
            {/* Nucleus */}
            <div 
              className="absolute w-24 h-24 bg-gradient-to-br from-red-500 to-yellow-500 rounded-full animate-pulse cursor-pointer transform transition-all duration-500 hover:scale-125 z-10"
              onMouseEnter={() => setHoveredPart('nucleus')}
              onMouseLeave={() => setHoveredPart(null)}
            ></div>
            
            {/* Electron orbits */}
            <div className="absolute w-64 h-64 border-4 border-blue-500 rounded-full animate-spin" style={{animationDuration: '8s'}}></div>
            <div className="absolute w-80 h-80 border-4 border-purple-500 rounded-full animate-spin" style={{animationDuration: '12s', animationDirection: 'reverse'}}></div>
            
            {/* Electrons */}
            <div className="absolute w-6 h-6 bg-blue-400 rounded-full top-1/2 left-8 animate-pulse cursor-pointer transform transition-all duration-500 hover:scale-150"
                 onMouseEnter={() => setHoveredPart('electron')}
                 onMouseLeave={() => setHoveredPart(null)}></div>
            <div className="absolute w-6 h-6 bg-blue-400 rounded-full bottom-12 right-20 animate-pulse cursor-pointer transform transition-all duration-500 hover:scale-150"
                 onMouseEnter={() => setHoveredPart('electron')}
                 onMouseLeave={() => setHoveredPart(null)}></div>
            <div className="absolute w-6 h-6 bg-purple-400 rounded-full top-8 right-8 animate-pulse cursor-pointer transform transition-all duration-500 hover:scale-150"
                 onMouseEnter={() => setHoveredPart('electron')}
                 onMouseLeave={() => setHoveredPart(null)}></div>
          </div>

          {/* Atom Parts Info */}
          <div className="space-y-6">
            {atomParts.map((part, idx) => (
              <div
                key={part.id}
                className={`p-6 transform transition-all duration-500 ${
                  hoveredPart === part.id || hoveredPart === 'nucleus' && (part.id === 'proton' || part.id === 'neutron')
                    ? 'bg-white text-black scale-105 rotate-0 translate-x-4'
                    : 'bg-gray-900 rotate-1 hover:rotate-0 hover:scale-105'
                }`}
                style={{ transitionDelay: `${idx * 50}ms` }}
              >
                <div className="flex items-center gap-4">
                  <div className={`w-4 h-4 ${part.color} transform rotate-45`}></div>
                  <div>
                    <h3 className="text-xl font-black tracking-wider">{part.name}</h3>
                    <p className="text-sm opacity-80">{part.desc}</p>
                  </div>
                </div>
              </div>
            ))}
          </div>
        </div>

        {/* Fun Facts Section */}
        <div className="mt-16 grid grid-cols-3 gap-6">
          {[
            { fact: 'ATOMS ARE 99.9% EMPTY SPACE', detail: 'Most of an atom is void between nucleus and electrons' },
            { fact: 'ATOMS NEVER TOUCH', detail: 'Electromagnetic forces keep them separated' },
            { fact: '7 BILLION BILLION BILLION', detail: 'Number of atoms in an average human body' }
          ].map((item, idx) => (
            <div 
              key={idx}
              className="p-6 bg-gradient-to-br from-gray-900 to-gray-800 transform rotate-2 transition-all duration-500 hover:rotate-0 hover:scale-105 hover:from-gray-800 hover:to-gray-700"
            >
              <h4 className="text-lg font-black mb-2 text-blue-400">{item.fact}</h4>
              <p className="text-sm text-gray-400">{item.detail}</p>
            </div>
          ))}
        </div>
      </div>
    </div>
  );
}
